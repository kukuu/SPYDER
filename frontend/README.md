# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

## Key changes in server2.js algorithm

Key changes made:

1. Created a constant initialReadings to store the initial values

2. Made the readings object a copy of initialReadings using the spread operator

3. Modified the generateReading function to check if the reading exceeds 10,000 kWh and reset to the initial value if it does

4. Added a console log message when a meter is reset

PS: Now whenever any meter's reading exceeds 10,000 kWh, it will automatically reset to its initial value (1000, 2000, or 3000 depending on the meter). The reset happens immediately when the threshold is crossed, before the reading is emitted to the client or saved to the database.

# Update Google Email AppScript template:

## Link:

 https://script.google.com/home/projects/1BqQObZn6QtLoHbH4BCxFRrAmcWmRcxG52muRMrUUpDLSRPbxvkvU5erU/edit

## Key changes made:

- Updated the labels as requested:

1. Changed "Customer Account Number" to "Customer Email"

2. Changed "Current Reading" to "Meter Reading(s)"

3. Improved the handling of multiple readings:

4. Now properly iterates through the meterData.readings array

5. Displays each reading with its date in a formatted block

6. Shows reading numbers (Reading #1, Reading #2, etc.)

- Enhanced the email UI:

1. Added better styling and structure

2. Improved visual hierarchy with colors and spacing

3. Added a proper footer with service branding

- Fixed the total cost calculation:

1. Now properly calculates the total across all readings

2. Displays it prominently in the email

- Added error handling:

1. 2. Better error logging

- Graceful handling of missing data: 

The script now properly matches the data structure being sent from your App.js component, where meterData.readings is an array of objects with value and date properties. Each reading will be displayed in the email with its corresponding date, and the total cost will be calculated across all readings.

The email template has been improved with better visual design while maintaining all the necessary information. The styling is inline to ensure compatibility across email clients.

No changes are needed to your App.js or App.css as the updated script works with the existing data structure you're sending. The only difference will be that the email will now properly display all the readings with their dates instead of showing undefined.

old:

```
function doPost(e) {
  try {
    const data = JSON.parse(e.postData.contents);
    const { userEmail, meterData } = data;
    const subject = "Your Energy Meter Reading Details";
    const htmlBody = `
      <h2>Energy Meter Reading Details</h2>
      <p>Here are your meter reading details for ${meterData.id}:</p>
      <p>Customer Account Number: ${meterData.accountNumber}</p>
      <div style="margin: 20px 0; padding: 20px; background-color: #f8f9fa; border-radius: 5px;">
        <h3>Current Reading: ${meterData.reading} kWh</h3>
        <p><strong>Supplier:</strong> ${meterData.supplier}</p>
        <p><strong>Tariff:</strong> ${meterData.tariff}</p>
        <p><strong>Cost per kWh:</strong> ${meterData.cost}p</p>
        <p><strong>Total Cost:</strong> £${meterData.total}</p>
      </div>
      
      <p>Thank you for using our service!</p>
    `;

    GmailApp.sendEmail(userEmail, subject, "", {
      htmlBody: htmlBody,
    });
    return ContentService.createTextOutput(
      JSON.stringify({
        success: true,
        message: "Email sent successfully",
      })
    ).setMimeType(ContentService.MimeType.JSON);
  } catch (error) {
    return ContentService.createTextOutput(
      JSON.stringify({
        success: false,
        error: error.message,
      })
    ).setMimeType(ContentService.MimeType.JSON);
  }
}
```

new:

```
function doPost(e) {
  try {
    const data = JSON.parse(e.postData.contents);
    const { userEmail, meterData } = data;
    const subject = "Your Energy Meter Reading Details";
    
    // Format the readings with dates
    let readingsHtml = '';
    meterData.readings.forEach((reading, index) => {
      const readingDate = reading.date || 'No date provided';
      const readingValue = reading.value || '0';
      readingsHtml += `
        <div style="margin-bottom: 10px; padding: 10px; background-color: #f0f0f0; border-radius: 5px;">
          <p><strong>Reading #${index + 1}:</strong> ${readingValue} kWh</p>
          <p><strong>Date:</strong> ${readingDate}</p>
        </div>
      `;
    });

    // Calculate total cost
    const totalCost = meterData.readings.reduce((sum, reading) => {
      const value = parseFloat(reading.value) || 0;
      return sum + (value * (meterData.cost / 100));
    }, 0).toFixed(2);

    const htmlBody = `
      <div style="font-family: Arial, sans-serif; max-width: 600px; margin: 0 auto; color: #333;">
        <h2 style="color: #2e7d32;">Energy Meter Reading Details</h2>
        <p>Here are your meter reading details for ${meterData.id}:</p>
        <p><strong>Customer Email:</strong> ${meterData.accountNumber || 'Not provided'}</p>
        
        <div style="margin: 20px 0; padding: 20px; background-color: #f8f9fa; border-radius: 5px; border-left: 4px solid #2e7d32;">
          <h3 style="color: #2e7d32; margin-top: 0;">Meter Reading(s):</h3>
          ${readingsHtml}
          
          <div style="margin-top: 20px; padding-top: 15px; border-top: 1px solid #ddd;">
            <p><strong>Supplier:</strong> ${meterData.supplier}</p>
            <p><strong>Tariff:</strong> ${meterData.tariff}</p>
            <p><strong>Cost per kWh:</strong> ${meterData.cost}p</p>
            <p style="font-weight: bold; font-size: 1.1em;"><strong>Total Cost:</strong> £${totalCost}</p>
          </div>
        </div>
        
        <p style="margin-top: 30px; font-size: 0.9em; color: #666;">
          Thank you for using our service!<br>
          <span style="color: #2e7d32; font-weight: bold;">SPYDER Energy Services</span>
        </p>
      </div>
    `;

    GmailApp.sendEmail(userEmail, subject, "", {
      htmlBody: htmlBody,
    });
    
    return ContentService.createTextOutput(
      JSON.stringify({
        success: true,
        message: "Email sent successfully",
      })
    ).setMimeType(ContentService.MimeType.JSON);
  } catch (error) {
    console.error("Error sending email:", error);
    return ContentService.createTextOutput(
      JSON.stringify({
        success: false,
        error: error.message,
      })
    ).setMimeType(ContentService.MimeType.JSON);
  }
}
```

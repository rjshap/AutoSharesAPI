Agreement Management in Custom Apps

Display agreements MUST BE SIGNED by traders prior to order placement

Introduction

Before traders can proceed to deposit funds into their trading account and start placing trades, they must first sign several mandatory agreements to comply with the policies of ETNA Trader, its partners, and the regulator. The process of preparing, signing, and managing these agreements is entirely taken care of by ETNA Trader. You, on the other hand, will need to take the following steps if you develop your own custom UI:
Check if there are outstanding agreements for the trader to sign
If so, display our own HTML page that walks the user through the signing procedure
Optionally provide ETNA with various information like the handler link, preferred theme, etc.

Step 1. Checking for Outstanding Agreements

The first step is to check if there are outstanding agreements that this user must sign. 
Checking for outstanding agreements must be performed every time the trader logs into the platform. Using ETNA Trader with unsigned agreements is strictly forbidden.
In response to this request you will receive the following array of agreements:
[
  {
    "Type": "Platform",
    "CanSkip": true
  }
]
There's no need to analyze the contents of the array; simply check if there are more than 0 items in it and, if so, proceed to step 2. If the array is empty, it means that there are no agreements to be signed and you may allow the trader into the app to start placing orders.

Step 2. Displaying the Agreements Page

The next step is to display the agreements page to the trader. The page itself along with the signing process is taken care of at our end while you simply need to display the following mark-up:


<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Agreements</title>
    <style>
        body {
            height: 100vh;
            width: 100vw;
            box-sizing: border-box;
            overflow: hidden;
            margin: 0;
        }
        #accountOpenning {
            height: 100vh;
            width: 100vw;
        }
    </style>
    <script type="text/javascript" src="AGREEMENTS_URL/assets/agreements.client.js"></script>
</head>
<body>
    <iframe
        id="agreements"
        src="AGREEMENTS_URL" <! --The URL of your agreements page on our server-->
        frameborder="0"
        name="agreements"
        scrolling='auto',
        allowfullscreen=true
        allow="geolocation;"
        appKey='%APPKEY%' <! --Your Et-App-Key-->
        token='%TOKEN%' <! --Token from the authentication endpoint-->
        theme='%THEME%' <! --Preferred theme ('Dark' or 'Light')-->
    ></iframe>
    <script>
        const
            frame = document.getElementById('agreements'),
            agreementsClient = new ETNA.AgreementsClient(frame),
            logger = agreementsClient.setLogger(data => {
                if (data.action === 'allAgreementsSignedOrSkipped') {
                    window.location.replace("%CUSTOM_URL%");
                    logger.remove();
                    return;
                    //Make custom actions here
                }
                if (data.type === 'info'){
                    console.log(data);
                    window.location.replace("%CUSTOM_URL%");
                    return;
                }
                if (data.type === 'error') return console.error(data);
            });
            agreementsClient.checkAgreements();
    </script>



As you can see, there are a few customizable feature in the form like the preferred theme, borders, name, etc. It is also possible to redirect the user to the URL specified in the CUSTOM_URL variable once the signing process is complete. If there's some JavaScript code that must be executed afterwards, that is also possible.

Step 3. Sending Customization Data to us.


Feel free to send the required preferences along with custom code to  and we'll get back to you with the final mark-up that you may then embed into your app and display it whenever there are outstanding agreements to be signed.

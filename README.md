// JavaScript File
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/html">
<scrip>
    <script src="https://sdk.amazonaws.com/js/aws-sdk-2.7.16.min.js"></script>
    <script src="js/aws-cognito-sdk.min.js"></script>
    <script src="js3/amazon-cognito-identity.min.js"></script>

    <script
        var idToken = null;

        function checkLogin(){
        var url_string + window.location.href;
        var url = new URL(url_string);
        idToken = url.searchParams.get("id_token");
        if(idToken != null) {

        document.getElementById ("WelcomeMsg").innerHTML = "Subscribe";
    auth();

    }
    }

    function auth(){
    AWS.config.update({
    region:"us-east-1",



    }};

    AWS.config.credentials = new AWS.CognitoIdentityCredentials({
    IdentityPoolId : ' us-east-1:858bacd7-5709-4397-a982-743bd52d07b2',
    Logins : {
           "cognito-idp.us-east-1.amazonaws.com/us-east-1_kA8wxdkSM
    ":idToken
    }
    }};

    }
function insertItem(){

var docClient = new AWS.DynamoDB.DocumentClient() ;

         var params = {
        TableName :"Person",
                     Item:{
                              "Email Address" : "",
                               "LastName"  :"",

"info": {

"FavoriteColor":"blue",
"YearOfBirth":1942


}}
};
docClient.put(params,function(err,data){
      if (err){
                 document.getElementById('textarea').innerHTML = "Unable to add item : " + "\n" + JSON.stringifylerr,undefined,2);

      } else {
    document.getElementById('textarea').innerHTML = "PutItem succeed : " + "\n" + JSON.stringifylerr,undefined,2);

}
}};


}

</scrip>
       </head>
             <body onload="CheckLogin()"></body>

             <div id="welcomeMsg"></div>
<a href="https://webappdnd.auth.us-east-1.amazoncognito.com/login?client_id=4gjfgjg6v31016oqfu3g5tsug2&response_type=token&scope=aws.cognito.signin.user.admin+email+openid+profile&redirect_uri=https://localhost:8080/"></a>
 <br></br>

<input type = "button" value="Insert Item" onclick="SelectNewsletter();"/>
<input type="button" value="Read Item" onclick="readNewsletter();"/>
<br></br>


     <textarea readonly id="textarea" style="width:400px;heaight:600px"></textarea>









</body>

</html>

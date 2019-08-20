# Getresponse-Api3-php

##How to add contacts into campaigns or lists
```
function httpAddContactToGetresponse($email,$name,$campaignId)
{
  $url = "https://api.getresponse.com/v3/contacts";
  $ch = curl_init();
  $vars=array("email"=>$email,"name"=>$name,
        "campaign[campaignId]"=>$campaignId,"dayOfCycle"=>"0"
        );
  curl_setopt($ch, CURLOPT_URL,$url);
  curl_setopt($ch, CURLOPT_POST, 1);
  curl_setopt($ch, CURLOPT_POSTFIELDS,$vars);  //Post Fields
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
  
  $headers = [
      'X-Auth-Token: api-key xxxxxxxxxxxxxxxxxxxxxxx'
  ];

  curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);

  $server_output = curl_exec ($ch);
  //error_log( print_r( $server_output, true ) );
  curl_close ($ch);
  return $server_output;
}
```


#Need any help, contact me : amankamboj2387@gmail.com

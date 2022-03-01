 
1.  создаю крон  - на который  делаю условие ( выполнять  обращение к файлу  каждые  пол часа - час )   -  подбирать файл  curl  лежащий в папке  -

 
2 .в  файл curl   - пишу   следующий код  - который  опрашивает  по  rest api    -  и  записывает и обновляет  данные


<?php

// Initializing curl
$curl = curl_init();

// Sending GET request to  
// server to get JSON data
curl_setopt($curl, CURLOPT_URL,
    "https://api.open-meteo.com/v1/forecast?latitude=55.7558&longitude=37.6176&hourly=precipitation&timezone=Europe%2FMoscow");

// Telling curl to store JSON
// data in a variable instead
// of dumping on screen
curl_setopt($curl,
    CURLOPT_RETURNTRANSFER, true);

// Executing curl
$response = curl_exec($curl);

// Checking if any error occurs
// during request or not
if($e = curl_error($curl)) {
    echo $e;
} else {

    // Decoding JSON data
    $decodedData =
        json_decode($response, true);

    // Outputing JSON data in
    // Decoded form
    var_dump($decodedData);
}

// Closing curl
curl_close($curl);
?>
 
на  основе  компонента  iblock.news   -  
создаю  новый который  будет  выводить  заданную в  параметрах  функциональность   - а именно условия  .    
по выводу -  времени и  осадков  - согласно  условиям  в  т.з.

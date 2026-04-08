<?php
$token = '8772686088:AAEhhWd-XHiplM6VLRE5EmdnYdIOgFq-plE';
$website = 'https://api.telegram.org/bot'.$token;

$input = file_get_contents('php://input');
$update = json_decode($input, TRUE);

$chatId = $update['message']['chat']['id'];
$message = $update['message']['text'];

switch($message) {
    case '/start':
        $response = 'PACIENCIA!!!';
        sendMessage($chatId, $response);
        break;

    case 'TE HA COSTADO HACER EL TRABAJO???':
        $response = 'DEMASIADO!!!';
        sendMessage($chatId, $response);
        break;

    default:
        $response = 'INTENTA PREGUNTAR OTRA COSA...';
        sendMessage($chatId, $response);
}

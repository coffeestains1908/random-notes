### SwiftMailer configuration
```
'mailer' => [
    'class' => 'yii\swiftmailer\Mailer',
    'useFileTransport' => false,
    'transport' => [
        'class' => 'Swift_SmtpTransport',
        'host' => '',
        'username' => '',
        'password' => '',
        'port' => 587,
        'encryption' => 'tls',
        'streamOptions' => [ 
            'ssl' => [ 
                'allow_self_signed' => true,
                'verify_peer' => false,
                'verify_peer_name' => false,
            ],
        ]
    ],
]
```

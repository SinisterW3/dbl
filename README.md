    }
    </style>
  </head>

  <body>
      <!-- Audio player container-->
     <div id='player'></div>

    <!-- Audio player js begin-->
    <script src="js/AudioPlayer.js"></script>

    <script>
        // test image for web notifications
        var iconImage = null;

        AP.init({
            container:'#player',//a string containing one CSS selector
            volume   : 0.7,
            autoPlay : true,
            notification: false,
            playList: [
                {'icon': iconImage, 'title': 'Try Everything', 'file': 'mp3/try-everything.mp3'},
                {'icon': iconImage, 'title': 'Let It Go', 'file': 'mp3/let-it-go.mp3'}
          ]
        });
    </script>
    <!-- Audio player js end-->

  </body>
</html>

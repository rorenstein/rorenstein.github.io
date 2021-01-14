<head>
    <link rel="apple-touch-icon" sizes="180x180" href="./apple-touch-icon.png">
    <link rel="icon" type="image/png" sizes="32x32" href="./favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="./favicon-16x16.png">
    <link rel="manifest" href="/site.webmanifest">
    <link rel="mask-icon" href="/safari-pinned-tab.svg" color="#5bbad5">
    <meta name="msapplication-TileColor" content="#00a300">
    <meta name="theme-color" content="#ffffff">
</head>

<style>
    .btn {
        background-color: #98f3ff;
        color: rgb(0, 0, 0);
        padding: 5px 10px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        margin: 4px 2px;
        cursor: pointer;}
    .filetype, .fname, .txtbox, .btn{
        font-family: sans-serif;
        font-size: medium;
    }
    .txtbox, .btn {
        border: none;
    }

</style>

<body>

    <input type="text" id="fname" name="fname" class="fname" value="File name">
    <a id="saveToFile" class="btn btn-primary">Save as...</a>
    <select name="filetype" id="filetype" class="filetype">
        <option value="txt">txt</option>
        <option value="md">md</option>
        <option value="csv">csv</option>
    </select>
    <br>
    <textarea type="text" id="txtin" name="txtin" class="txtbox" rows="20" cols="100">write here...</textarea>

    <script src="http://code.jquery.com/jquery.js"></script>

    <script>
        $(function() {
          $('#saveToFile').click(function(e) {
            var data = document.getElementById('txtin').value;
            var ftype = document.getElementById('filetype').value;
            var filename = document.getElementById('fname').value;
            var data = 'data:application/'+ftype+';charset=utf-8,' + encodeURIComponent(data);
            var el = e.currentTarget;
            el.href = data;
            el.target = '_blank';
            el.download = filename+'.'+ftype;
            
          });
        });
        </script>

</body>

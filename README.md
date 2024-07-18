# Serial-Generator
This code generates numers in a series  with setInterval


<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Serial-number</title>
    <style>
        body {
            text-align: center;
        }

        .content {
            /* border: 1px solid; */
            height: auto;
        }

        .content>p {
            border: 1px solid green;
            height: 5vh;
        }
    </style>
</head>

<body>
    <div class="content">

        <h1>Everything Appears here</h1>
        <p></p>
        <p></p>
    </div>
    #javaScript Code
    <script>

        // variables and dom
        let randnum;
        let dis = document.querySelectorAll(".content")[0].children[1];
        let sdis = document.querySelectorAll(".content")[0].children[2];
        let randarray = [];
        let x = 0;


        // interval to execute program repeatedaly
        let a = setInterval(() => {

            // generating random number
            randnum = Math.floor(Math.random() * 30 + 1);
            // displaying the random number to see
            sdis.innerHTML = randnum;

            // checking if the random number
            if (randnum == x + 1) {

                // if the random number is in row or not if in a serial row pushing it to the array
                randarray.push(randnum);

                // increasing the value of x to get push the next number after one nuumber is being pushed
                x = x + 1;

                // when numbers upto 25 is pushed to the array clearing the interval
                if (x == 25) {

                    sdis.innerHTML = 'Completed';
                    sdis.style.backgroundColor = 'green';


                    clearInterval(a);
                    dis.style.backgroundColor = 'gray';
                }

            }
            // displaying the pushed numbers update
            dis.innerHTML = randarray;
        }, 100)
    </script>
</body>

</html>

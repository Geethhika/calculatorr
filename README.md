<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator bolte!!!</title>
    <style>
        h1{
            color: white;
            font-size: 50px;
            text-align: center;
        }
        
        .cont{
            border-radius: 9px;
           margin: 0 auto;
            margin-top:60px;
            border: 30px solid aqua;
            font-size:xx-large;
            font-weight: 600;
            display: grid;
            width: 50vw;
            height: 500px;
            background-color: aqua;
            text-align: center;
            grid-template-areas: 
            "a a a a"
            "b c d e"
            "f g h t"
            "j k l q"
            "m n o i"
            "s p r i"
            ;
        }
        @media only screen and (min-width: 1001px){
            .cont{
                width: 30vw;
               
            }
        }
        @media only screen and  (max-width:600px){
            .cont{
                margin: 0 auto;
                width: 80vw;
            }
        }
        #a,#b,#c,#d,#e,#f,#g,#h,#i,#j,#k,#l,#m,#n,#o,#p,#q,#r,#s,#t{
            padding-top: 25px;
            border: 1px solid gray;
            background-color: white;
        }
        
        #a{
            grid-area:a ;
            background-color: black;
            color: white;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
            padding:20px;
            text-align: end;

        }
        #b{
            grid-area: b;
            background-color: rgb(221, 220, 220);

        }
        #c{
            grid-area: c;
            background-color: rgb(221, 220, 220);
            padding-top:22px ;

        }
        #d{
            grid-area: d;
            background-color:  rgb(221, 220, 220);
            padding-top:25px ;
        }
        #e{
            grid-area: e;
            background-color:  rgb(221, 220, 220);
        }
        #f{
            grid-area: f;
        }
        #g{
            grid-area: g;
        }
        #h{
            grid-area:h ;
        }
        #i{
            
            grid-area: i;
            border-bottom-right-radius: 10px;
            padding-top: 60px;
            background-color: rgb(230, 100, 52);
            
            
        }
        #j{
            grid-area:j ;
        }
        #k{
            grid-area: k;
        }
        #l{
            grid-area: l;
            
        }
        #m{
            grid-area: m;
        }
        #n{
            grid-area: n;
        }
        #o{
            grid-area: o;
        }
        #p{
            grid-area: p;
            
        }
        #q{
            grid-area: q;
        }
        #r{
            grid-area: r;
        }
        #s{
            grid-area: s;
            border-bottom-left-radius: 10px;
        }
        #t{
            grid-area: t;
        }
        .same:hover{
            color: rgb(37, 16, 232);
        }
        
    </style>

</head>
<body>
    <div class="cont">
        <div class="same" id="a">0</div>
        <div class="same" id="b">+</div>
        <div class="same" id="c">-</div>
        <div class="same" id="d">*</div>
        <div class="same" id="e">/</div>
        <div class="same" id="f">7</div>
        <div class="same" id="g">8</div>
        <div class="same" id="h">9</div>
        <div class="same" id="i">=</div>
        <div class="same" id="j">4</div>
        <div class="same" id="k">5</div>
        <div class="same" id="l">6</div>
        <div class="same" id="m">1</div>
        <div class="same" id="n">2</div>
        <div class="same" id="o">3</div>
        <div class="same" id="p">0</div>
        <div class="same" id="q">.</div>
        <div class="same" id="r">AC</div>
        <div class="same" id="s">C</div>
        <div class="same" id="t">%</div>
        
    </div>
</body>
<script>
    // Get all the calculator buttons
    const buttons = document.querySelectorAll('.same');

    // Get the display element
    const display = document.getElementById('a');
    let string='';

    buttons.forEach(button => {
        button.addEventListener('click', (e) => {
            if (button.textContent === "=") {
                try {
                    string=eval(string);
                    document.querySelector('#a').innerHTML=string;
                } catch (error) {
                  document.querySelector('#a').innerHTML="Error";
                }
              }
            else if(e.target.innerHTML=="AC"){
                string="";
                document.querySelector('#a').innerHTML=string;
            }
            else if(e.target.innerHTML=="C"){
                string=string.slice(0,-1);
                console.log(string)
                document.querySelector('#a').innerHTML=string;
            }
            else{
            console.log(e.target)
        string=string+e.target.innerHTML;
        document.querySelector('#a').innerHTML=string;
    }
        });
    });

   
</script>
</html>

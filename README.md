
<html>
<head>
<title>Productos electrónicos</title> 
</head>
<body>
	<style type="text/css">
* { margin: auto; padding: 0; text-align: center }
#cabecera { font: bold 1.3em verdana; background-color: #F8F1ED;  }
h1 { text-align: center ; padding: 0.5em }
#menu { float: left; width: 25%; background-color: #F9E4D6; }
#menu img { width: 35%; margin: 5%; cursor: pointer; }
#principal { float: left; width: 75%; }
#visor { width: 60%; margin: 10% }
#visor img { width: 100% }
</style>
<script type="text/javascript">
window.onload = function() { //tras cargar la página ...
visor1=document.getElementById("visor"); //referencia al visor
mititulo=document.getElementById("titulo"); //referencia al pie de foto
}
function mifoto(num) { //cambiar la imagen
         f="foto"+num+".jpg"; //ruta de la nueva imagen
         document.images["fotoVisor"].src=f; //cambiar imagen
         t=document.images["fotos"+num].alt; //texto de pie de foto
         mititulo.innerHTML=t; //cambiar pie de foto
         }
</script>
<div id="cabecera">
<h1>Productos electrónicos</h1>
</div>
<div id="menu">
<img src='foto1.jpg' alt='1. COWIN E7 Audífonos con cancelación activa de ruido, con Bluetooth y micrófono de bajo profundo, inalámbricos, estilo orejera, con almohadillas protectoras, 30 horas de reproducción para viaje/trabajo, negro. Precio B/59.99.' name='fotos1' onclick="mifoto(1)"/>
<img src='foto2.jpg' alt='2. SANSUI ES32S1N - Televisor LED inteligente de 32 pulgadas 720p Televisión de alta resolución HDMI incorporado, USB - Soporte de pantalla de espejo (modelo 2020). Construido con panel HD para imágenes nítidas y detalladas cuando reproduce contenido multimedia compatible, hace que tus ojos estén más cómodos cuando estás viendo imágenes, aliviando la fatiga causada por un reloj de larga duración. Precio B/139.99.' name='fotos2' onclick="mifoto(2)"/>
<img src='foto3.jpg' alt='3. UBeesize Selfie Stick Trípode extensible de 51 pulgadas con control remoto Bluetooth para teléfonos celulares, ideal para selfies, fotos de grupo, viajes de aventura, vlogging, vídeos de YouTube, podcasts, Facebook Live, FaceTime, Instagram, transmisión en directo. Precio B/24.99.' name='fotos3' onclick="mifoto(3)"/>
</div>
<div id="principal">
<div id="visor">
   <img src='foto1.jpg' alt='1. COWIN E7.' name='fotoVisor'/>
   <div id="titulo">1. COWIN E7.</div>
   </div>
   <script>
    function factura(){
      var d = new Date();
      var nfac = 0;
      var nombrec = document.getElementById('nombre_cliente').value;
      var idc = document.getElementById('id_cliente').value;
      var tlfc = document.getElementById('telefonoc').value;
      var direc = document.getElementById('direccionc').value;
      var producto;
      var cantidadp = new Number();
      var a = 0;
      var cantidad;
      var precio = [];
      var i = 0;
      var suma = 0;
      var total = 0;
      var iva;
      var subtotal;
      var pago;
      nfac = Math.floor(Math.random()*999999999);
      document.write('<strong>Numero de factura: </strong>' +nfac+'<br>');
      document.write('<strong>Fecha: </strong>');
      document.write(d.getDate());
      document.write('/');
      document.write(d.getMonth());
      document.write('/');
      document.writed(d.getFullYear());
      document.write(' ');
      document.write(d.getHours());
      document.write(':');
      document.write(d.getMinutes());
      document.write(':');
      document.write(d.getSeconds()+'<br>');
      pago =(prompt('Digite forma de pago. (Tarjeta o Efectivo)'));
      document.write('<strong>Forma de pago: </strong>'+pago);
      document.write('<h1>------Datos del cliente-------</h1>');
      document.write('<strong>Nombre del cliente: </strong>'+nombrec+'<br>');
      document.write('<br><strong>Id del cliente: </strong>'+idc+'<br>');
      document.write('<br><strong>Direccion del cliente: </strong>'+direc);
      document.write('<h1>------Productos a llevar-------</h1>');
      while(i==a){
        producto = prompt('Ingrese producto.');
        cantidadp = prompt('Ingrese cantidad de '+producto+'.');
        precio[i] = parseInt(prompt('Ingrese precio del producto.'));
        document.write('<strong>Producto: </strong>'+producto+'<strong>Cantidad: </strong>'+cantidadp+'<strong> Precio: </strong>'+precio[i]+'<strong>')
        a = prompt('Para continuar la factura ingrese: "0" y para terminar marque cualquier numero.');
        suma = suma+precio[i] ;
        subtotal = cantidadp*suma;
        iva = subtotal*0.19;
        total = subtotal+iva; 
      }
      document.write('<h2>-------------------------------------------------</h2>');
      document.write('<br><h3>IVA: '+iva+'</h3>');
      document.write('<br><h3>Subtotal: '+subtotal+'</h3>');
      document.write('<h2><br>Total: '+total+'</h2>');
      document.write('<br>button onclick="window.print()">Imprimir</button>');

    }
    factura();
  </script>
  </head>
  <body>
    <h1>Datos del Cliente:</h1>
    <br/>Nombre :<br/><input type="text" id="nombre_cliente" placeholder="Ingrese nombre del cliente"><br/><br/>
         Id: <br/><input type="text" id="id_cliente" placeholder="Ingrese id del cliente."><br/><br/>
         Telefono: <br/><input type="text" id="telefonoc" placeholder="Ingrese telefono del cliente."><br/><br/>
         Id: <br/><input type="text" id="direccionc" placeholder="Ingrese direccion del cliente."><br/><br/>
         <br/><br/><input onclick="factura()" type="submit" value="Enviar">
  </body>
</div>
</body>
</html>

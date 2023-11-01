<h3>React Router</h3>
<p>
    React Router es una librería que se utiliza bastante con React y que nos facilita el proceso de definir las rutas de navegación dentro de nuestra aplicación. Al igual que el propio React, esta librería (react router) usa una metodología declarativa en vez de imperativa.
</p>
<br><b>01. Instalar React Router</b> - Utilizaremos el instalador de Node.js a través de npm (también se puede utilizar cualquier otro manejador de paquetes, yarn, pmpm, etc.) Hay que instalarlo en el directorio de nuestro proyecto.

````JSX
npm i react-router-dom
````
<p><b>02. Importar el componente React Router</b> - Luego de instalar react-router-dom, vamos a proceder a importarlo dentro de nuestro archivo Main.jsx o aquel que hayamos definido como manejador principal de componentes.</p>

````JSX
import { BrowserRouter } from "react-router-dom";
````
<p><b>03. Aplicar Browser Router en Main.jsx</b> - Para comenzar a utilizar la navegación debemos envolver nuestros componentes que van a aparecer en Main.jsx con BrowserRouter en lugar de usar React.StrictMode</p>


````JSX
import React from 'react';
import ReactDOM from 'react-dom';
import './indice.css';
import App from './Aplicacion';
import { BrowserRouter } from "react-router-dom";

ReactDOM.render(
    <BrowserRouter>
      //mis componentes a mostrar
      <App />
    </BrowserRouter>
)
````
<p>De esta manera estamos importando el componente BrowserRouter en la raiz de nuestra aplicación.</p>
<p><b>04. Utilización de Link, Route y Routes</b> - El primer paso es importar dentro de App.jsx los componentes desde la libreria react-router-dom.<br>
<br>Para navegar entre distintas "páginas" utilizabamos la etiqueta Anchor <b> a href</b>, en la cual le indicábamos una ruta específica hacia donde dirigirse. <p>En React vamos a utilizar el componente <b>Link</b>.
También le vamos a poder asignar estilos mediante className.</p></p>

````JSX
<Link className='boton' href="/galeria"></Link>
````

<p>Por otro lado, debemos definir nuestras rutas hacia donde apuntar los Links. Para ello utilizaremos Routes en dónde Route será el destino de cada componente. Ambas etiquetas deben cerrarse.
</p>

````JSX
import {Link, Route, Routes} from 'react-router-dom'
export const App (){
    return(
        <Routes>
            <Route index path="/" element={<Main />} />
            <Route path="/nosotros" element={<Nosotros />} />
            <Route path="/contacto" element={<Contacto />} />
        </Routes>
    )
}
````
<p>
    Route está compuesto por dos partes, la ruta --> <i>path="/nombreruta"</i> que será la dirección que utilizaremos en la etiqueta Link.<br>
También debemos definir que componente va a mostrarse y para ello agregamos el atributo <i>element={Componente}</i>, será en donde indicaremos que componente debe "llamar".
</p>

````JSX
<Route path="/nosotros" element={<Nosotros />} />
````

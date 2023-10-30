# comboVenta
<div>
    <form method="$_POST">
        <div>
            <label>Fecha venta:</label>
            <input type="date" name="txtFecha">
        </div>
        <div>
            <label>Cliente :</label>
            <select name="cboCliente">
                <option value="pepito">Jose</option>
                <option value="Anita">Anita perez</option>
                <option value="Lucho">zeya</option>
                <option value="Shirley">Zuley</option>
            </select>
        </div>
        <div>
            <label>Producto:</label>

            <select name="cboProducto">
                <option value="tallarin">Tallarin sumesa</option>
                <option value="Atun">Atun</option>
                <option value="deja">deja</option>
                <option value="pan">pan</option>
                <option value="caramelo">caramelos</option>
            </select>
        </div>
        <div>
            <label>Cantidad :</label>
            <input type="number" name="txtCanti">
        </div>
        <div>
        <label>Precio :</label>
            <input type="text" name="txtPrecio">
        </div>
        <div>
        <button>Calcular :</button>
        </div>
        <hr>
        <h1>***RESULTADOS***</h1>
        <?php
        if(isset($_POST['btnCalcular'])){
            $Fecha= $_POST['txtFecha'];
            $Cliente=$_POST['cboCliente'];
            $producto=$_POST['txtCanti'];
            $Cantidad= $_POST['txtCanti'];
            $Precio=$_POST['txtPrecio'];
            $subTot=$Cantidad*$Precio;
            $iva= $subTot*0.12;
            $desc=0;
            
            if($subTot<50){
             $desc=$subTot*0.05;
             $regalo="No tiene regalo";
            } else{
            if($subTot>=50 &&$subTot<100)
             $desc=$subTot*0.07;
             $regalo="Pelota";
            }
            } else {
            if($subTot >=100 &&$subTot <200)
              $desc=$subTot*0.01;
              $regalo="licuadora";
            } else {
             $desc=$subTot*0.15;
             $regalo="viaje a venezuela";
            } 
               

$totPagar= $subTot+$iva- $desc;
        //***Resultados***/
        echo "Fecha    :" .$Fecha ."<br>;
        echo "Cliente  :" .$cliente."<br>;
        echo "Producto :" .$Producto."<br>;
        echo "SubTotal :" .$Fecha ."<br>;
        echo "iva 12%  :" .$Fecha ."<br>;
        echo "Fecha :" .$Fecha ."<br>;
    </form>
</div>

# appGestionPequeñoNegocio
Se crea la clase clsConexionBD.cs
Luego ponemos esta librería al inicio:
using System.Data.SqlClient;

//conector
SqlConnection conexionBaseDatos;

//comando
SqlCommand comandoBaseDatos = "Server=myServerAddress;Database=myDataBase;Trusted_Connection=True"; //aca se cambia el nombre de myDataBase por el nombre de archivo de la BD.


public void ConectarBD() {
	//acá va la cadena de conexión
	conexionBaseDatos = new SqlConnection(cadenaConexion);
	nombreBaseDeDatos = conexionBaseDatos.Database;
	conexionBaseDatos.Open();
}
	
connectionstrings.com/sql-server/ => trusted connection, copio y pego eso en "cadenaConexion".

Luego vamos a administrador de tareas, buscar el servicio MSSQLSERVER e iniciarlo.

luego en frmMain o principal, en evento Load, hay que instanciar la base:
	clsConexionBD objConectarBD = new clsConexionBD();
	objConectarBD.ConectarBD();
	MessageBox.Show("Conectado a ...");

-¿Cómo restaurar base de datos a partir de un archivo? (ejemplo ventas.bak)

Hay que abrir sql server, una vez abierto y a la carpeta Base de Datos, click derecho y "restaurar base de datos". Allí dentro seleccionar el archivo de BD que queremos abrir. Origen => dispositivo. Click en los puntos ... luego en "Agregar" y buscamos el archivo .bak . ACEPTAR, ACEPTAR, ACEPTAR. (Asegurarse de que el servicio sql este andando).


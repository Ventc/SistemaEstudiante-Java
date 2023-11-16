# SistemaEstudiante-Java

**Este código Java es una implementación básica para establecer una conexión a una base de datos MySQL utilizando JDBC (Java Database Connectivity). Aquí hay una explicación breve del código:**

**Importaciones:**

`package UTN.conexion;`
`import java.sql.Connection;`
`import java.sql.Driver;`
`import java.sql.DriverManager;`
`import java.sql.SQLException;`

**Estas líneas importan las clases necesarias para la gestión de conexiones JDBC.**

======================================================================================

**Clase Conexion:**

`public class Conexion {`

**La clase Conexion contiene un método estático llamado getConnection que devuelve un objeto de tipo Connection, que es utilizado para interactuar con la base de datos.**

======================================================================================

**Parámetros de conexión:**

````
var baseDatos = "estudiantes";
var url = "jdbc:mysql://localhost:3306/" + baseDatos;
var usuario = "root";
var password = "admin";
````
**Estos son los parámetros necesarios para establecer la conexión a la base de datos. baseDatos representa el nombre de la base de datos, url es la URL de conexión JDBC para MySQL, y usuario y password son las credenciales de acceso.**

======================================================================================

**Carga del controlador (Driver):**

````
try {
    Class.forName("com.mysql.cj.jdbc.Driver");
    conexion = DriverManager.getConnection(url, usuario, password);
} catch (ClassNotFoundException | SQLException e) {
    System.out.println("Ocurrió un error en la conexión: " + e.getMessage());
}
````
**En este bloque, se carga dinámicamente el controlador (Driver) de MySQL en memoria utilizando Class.forName. Luego, se utiliza DriverManager.getConnection para establecer la conexión a la base de datos con los parámetros proporcionados.**

======================================================================================

**Manejo de excepciones:**

````
} catch (ClassNotFoundException | SQLException e) {
    System.out.println("Ocurrió un error en la conexión: " + e.getMessage());
}
````
**En caso de que ocurra una excepción durante la carga del controlador o la conexión, se captura la excepción y se imprime un mensaje de error.**

======================================================================================

**Retorno de la conexión:**

`return conexion;`

**Finalmente, el método devuelve el objeto de conexión (Connection) que puede ser utilizado para realizar operaciones en la base de datos.**

======================================================================================

**Es importante tener en cuenta que este código utiliza la antigua forma de cargar el controlador (Class.forName) y puede no ser necesario en versiones más recientes de JDBC. Además, deberías cerrar la conexión (Connection) cuando hayas terminado de usarla para evitar posibles problemas de recursos. Puedes hacer esto en un bloque finally o utilizando el try-with-resources de Java.**










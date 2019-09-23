## Nomenclatura

- No utilice la `Hungarian Notation` ni ningún `guión bajo` en los nombres de las variables. C# es un lenguaje fuerte, no es necesario marcar campos con sus tipos en sus nombres. Y casi todos los editores de código proporcionan resaltado de código e información sobre herramientas, puede aprender fácilmente el tipo de una variable hoovering en su nombre.

  ```csharp
  // No Usar
  public float f_count;
  private string m_itemName;

  // Usar
  public float count;
  private string itemName;
  ```
  
  ---
- No use `números` en los nombres. Escriba el nombre del número en lugar del número en sí. Esto causa un problema, especialmente en algunas fuentes donde `número cero y letra mayúscula o` y` número uno y letra l` parecen similares. La mejor práctica es evitar el uso de números en los nombres.

  ```csharp
  // No Usar
  private bool isCount0;
  private string 1stItem;

  // Usar
  private bool isCountZero;
  private string firstItem;
  ```
  
  ---
- Los nombres de `Clases`, `Constructores`, `Estructuras` e `Interfaces` deben estar en `PascalCase`.
  ```csharp
  public class ExampleClass: MonoBehaviour, IExample
  {
    public ExampleClass
    {
      ...
    }
  }

  public interface IExample { }

  public struct DataContainer { }
  ```
  ---
- Los nombres de `Métodos` deben estar en `PascalCase`.
  ```csharp
  public class ExampleClass
  {
    public int SumNumbers(int a, int b)
    {
      ...
    }
  }
  ```
  ---
- Los nombres de `Campos`, `Variables Locales` y `Parametros` deben estar en `camelCase`.
  ```csharp
  public class ExampleClass 
  {
    private int firstNumber;
    private int secondNumber;

    private int MultiplyNumbers(int firstParameter, int secondParameter)
    {
      var localResult = firstParameter * secondParameter;

      return localResult;
    }
  }
  ```
  ---
- Los nombres de `Delegados` y `Eventos` deben estar en `PascalCase`.
  ```csharp
  public class ExampleClass
  {
    public delegate int SubtractNumbers(int x, int y);
    public event Func<int, int, int> MultiplyNumbers;
  }
  ```
  ---
- `Propiedades` deben estar en `PascalCase`
  ```csharp
  public class ExampleClass
  {
    public string OperationName { get; set; }
    public float OperationTime { get; set; }

    private int count;
    public int Count
    {
      get 
      {
        return count;
      }

      set
      {
        count = value;
      }
    }
  }
  ```
  ---
- Los nombres de `Enumeradores` y `Valores` deben estar en `PascalCase`.
  ```csharp
  public enum CalculationOperators
  {
    MultiplicationOperator,
    DivisionOperator,
    SubtractionOperator,
    SummationOperator
  }
  ```
  ---
- Los nombres de `Constantes`, `Estaticos` y `Readonly` deben estar en `PascalCase`.
  ```csharp
  public class ExampleClass 
  {
    private const int ConstantNumber;
    private readonly int ReadonlyNumber;
    private static int StaticNumber;
    private int variableNumber;
  }
  ```

  ---
- No use `Prefijos` en los nombres. Use `Sufijos`. El uso de prefijos hace que todos los nombres se vean similares y requiere atención adicional ya que leemos de izquierda a derecha.


  ```csharp
  // No Usar
  public class ExampleClass 
  {
    private object providerFile;
    private object providerInfo;
    private object providerTool;
  }

  // Usar
  public class ExampleClass 
  {
    private object fileProvider;
    private object infoProvider;
    private object toolProvider;
  }
  ```

  ---
- Agregue el sufijo `Async` a los nombres de `Corrutinas`. Esto le ayudará a dar el mismo nombre a su método de llamada y a su rutina. Aunque este sufijo no debe confundirse con la palabra clave `async`.

  ```csharp
  // No Usar
  private IEnumerator CoroutineLoadCatPictures() { ... }
  private IEnumerator C_LoadCatPictures() { ... }
  private IEnumerator CoLoadCatPictures() { ... }
  ...

  // Usar
  public void LoadCatPictures()
  {
    StartCoroutine(LoadCatPicturesAsync());
  }

  private IEnumerator LoadCatPicturesAsync()
  {
    ...
  }
  ```
  ---
- No utilice 'nombres abreviados' o 'abreviaturas poco comunes'. Los nombres deben ser claros y entendibles. Deben transmitir la idea correcta al lector.
  
  ```csharp
  // No Usar
  private int ic;
  private string uiid;

  // Usar
  private int itemCount;
  private string uniqueItemId;
  ```

  ---

## Convenciones de estilo
- Favorezca `espacios` sobre `tabulaciones` para la sangría. El número de columnas en las tabulaciones puede diferir según el entorno, sin embargo, un espacio siempre es una columna. Puede configurar cuántos espacios debe ser igual a una tabulación, luego puede seguir usando el botón de tabular para insertar múltiples espacios.

  ---
- Inserte las `llaves para encapsular` en nuevas líneas en lugar de justo después de los nombres de clase de los métodos.

  ```csharp
  // No Usar
  public class MyClass {
    private int myVar;

    private int Calculate() {
      myVar = 0;
      
      if(oldVar > 0) {
        ...
      }
    }
  }

  // Usar
  public class MyClass
  {
    private int myVar;

    private int Calculate()
    {
      myVar = 0;
      
      if(oldVar > 0)
      {
        ...
      }
    }
  }
  ```

  ---
- Inserte nuevas líneas después de cada método para aumentar la legibilidad. Puede mantener los campos relacionados en grupos e insertar una nueva línea después de un grupo para marcar la separación de contextos. No inserte más de una línea vacía.

  ```csharp
  public class MyClass
  {
    private int firstNumber;
    private int secondNumber;

    private string userInput;
    private int maxNumberOfInputs;
    private InputReader inputReader; 

    private void Execute()
    {
      ...
    }

    public void Operate()
    {
      ...
    }
  }
  ```
  ---
- Utilice siempre el modificador de acceso `privado` cuando tenga estructuras privadas. En C #, cualquier estructura sin uno de los modificadores de acceso `publico`,` protegido`, `interno` se considera `privada`. Sin embargo, no usar 'privado' disminuye la legibilidad.
  ```csharp
  // No Usar
  int firstNumber;
  int numberCount;

  int Count() { ... }

  // Usar
  private int firstNumber;
  private int numberCount;

  private int Count() { ... }
  ```
  ---
- Use paréntesis para que las condiciones sean más aparentes.

  ```csharp
  bool active = (count > number);

  if (active && (count > 0))
  {
    ...
  }
  ```
  ---
- Si necesita usar una cadena de métodos y la declaración se está volviendo más larga, puede dividirla desde puntos y pasar a la siguiente línea.

  ```csharp
  int result = Calculator.Operations.Initialize(7)
    .Multiply(4)
    .Divide(5);
  ```
  ---

## Consejos de Idioma y Unity
- Use `this` para referencias locales de campos cuando existan parámetros con el mismo nombre. Evite el uso de guiones bajos en los nombres de los parámetros.

  ```csharp
  // No Usar
  private int capacity;

  public MyConstructor(int _capacity)
  {
    capacity = _capacity;
  }

  // Usar
  private int capacity;

  public MyConstructor(int capacity)
  {
    this.capacity = capacity;
  }
  ```
  
  ---
- No use en exceso el tipo `var`, especialmente cuando el tipo de la variable es obvio. Úselo para tipos largos de variables locales y tipos `dinámicos (anónimos)`.

  ```csharp
  var empty = new EmptyInventoryItemContainer();

  var jsonPayload = new
  {
    name = "John",
    surname = "Doe"
  }
  ```
  ---
- Utilice `interpolación de cadenas` para crear cadenas cortas.
  ```csharp
  string message = $"Welcome { name }, you are { minutes } late!";
  ```
  ---
- Si se trata de cadenas muy largas, y tal vez usar bucles para crear cadenas usando `StringBuilder` será más eficiente.
  
  ---
- Puede usar una inicialización de matriz manual corta sin volver a escribir el tipo.

  ```csharp
  string[] names = { "george", "amy", "joe" };
  ```

  ---
- Use `namespaces` para encapsular su funcionalidad y objetos del mismo contexto. Esto lo ayudará a mantener las cosas ordenadas y evitar confusiones en caso de que otras bibliotecas que pueda usar tengan nombres de clase similares.
  
  ---
- Si su proyecto necesita conexión a Internet, verifíquelo siempre antes de realizar una solicitud web. Y siempre cubra los casos exitosos y fallidos de solicitudes web y luego notifique al usuario en consecuencia.

  ---
- A menos que sea ciertamente necesario, todos sus archivos en una clase deben ser privados. Para poder mostrar sus campos en el inspector de Unity, use el atributo `[SerializeField]`.
  
  ```csharp
  // No Usar
  public int count;

  // Usar
  [SerializeField] private int count;
  ```

  ---
- Use inicializadores de objetos para simplificar la configuración de los valores predeterminados de un objeto.

    ```csharp
    // No Usar
    Item item = new Item();
    item.name = "Box";
    item.weight = 10;
    item.volume = 5;

    // Usar
    Item item = new Item() {name = "Box", weight = 10, volume = 5};
    ```
    ---
- Si tiene una variable pública que solo debe modificarse en su objeto, use 'public get, private set property' para definirla.

  ```csharp
  public Count { get; private set; }
  ```
  ---
- Si tiene una variable que debería ser la misma para todas las instancias de ese objeto cuando se modifica, use la palabra clave `static`.

  ```csharp
  private static int Count; 
  ```
  ---
- Si tiene una variable que solo debe leerse y su valor nunca debe modificarse, use la palabra clave `const`.

  ```csharp
  private const int Capacity;
  ```
  --- 
- Si tiene una variable que debería leerse, pero su valor se decide cuando se construye el objeto, use la palabra clave `readonly`.

  ```csharp
  private readonly int Capacity;
  ```
  ---
- Cree el caché de los miembros o propiedades que utiliza dentro de los bucles.

  ```csharp
  // No Usar
  private Update()
  {
    SetDistance(Player.position.x, currentPosition.x);
  }

  // Usar
  private float positionX = Player.position.x;

  private Update()
  {
    SetDistance(positionX, currentPosition.x);
  }
  ```
  ---

- Utilice el método `CompareTag` en lugar del miembro `tag`. El método CompareTag no genera basura.

  ```csharp
  // No Usar
  void OnTriggerEnter(Collider other)
  {
      bool isPlayer = (other.gameObject.tag == "Player");
  }

  // Usar
  void OnTriggerEnter(Collider other)
  {
      bool isPlayer = other.gameObject.CompareTag("Player");
  }
  ```
  ---
- Evite arrojar 'null' o '0' en las rutinas que causan la creación de basura. También usar la palabra clave `new` varias veces causa pérdida de rendimiento, guarde en caché su declaración `WaitForSeconds`.

  ```csharp
  private WaitForSeconds delay = new WaitForSeconds(2);

  private IEnumerator OperationAsync()
  {
    ...

    while (!isDone)
    {
        yield return delay;
    }
  }
  ```
  ---
- Evita usar corrutinas para animaciones. Simplemente use Unity `Animator` y` Animations` para hacer tales tareas.

  ---
- Evite usar `bucles foreach` donde tenga matrices o listas muy largas para recorrer en iteración, y use `for loops`. Los bucles Foreach generan una pequeña cantidad de basura.
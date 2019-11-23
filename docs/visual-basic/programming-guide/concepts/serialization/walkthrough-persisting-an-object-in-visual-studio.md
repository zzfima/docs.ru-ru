---
title: Сохранение объекта в Visual Studio
ms.date: 07/20/2015
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
ms.openlocfilehash: fbd342c929e8519571c0f6bb76d4091efcfe4476
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350397"
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a>Пошаговое руководство. Сохранение объекта в Visual Studio (Visual Basic)
Несмотря на то, что во время разработки свойствам объекта можно задать значения по умолчанию, любые значения, введенные во время выполнения, будут потеряны при уничтожении объекта. С помощью сериализации можно сохранить данные объекта между экземплярами, что позволит сохранять значения и извлекать их при следующем создании экземпляра объекта.  
  
> [!NOTE]
> В Visual Basic можно использовать объект `My.Settings` для хранения простых данных, таких как имя или число. Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
 В этом пошаговом руководстве будет создан простой объект `Loan`, а его данные сохранены в файл. Затем при повторном создании объекта вы получите данные из файла.  
  
> [!IMPORTANT]
> В этом примере создается файл (если файл отсутствует). Если приложение должно создать файл, ему необходимо разрешение `Create` для папки. Для задания разрешений используются списки управления доступом. Если файл уже существует, приложению требуется лишь разрешение `Write` (с более низким уровнем). Если возможно, безопаснее создать файл во время развертывания и предоставить только разрешение `Read` для одного файла (вместо разрешения Create для папки). По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в коревую папку или папку Program Files.  
  
> [!IMPORTANT]
> В этом примере данные сохраняются в двоичном формате. Эти форматы не следует использовать для конфиденциальных данных, таких как пароли или сведения о кредитных картах.  
  
> [!NOTE]
> Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-loan-object"></a>Создание объекта Loan  
 Первым шагом является создание класса `Loan` и тестового приложения, которое использует класс.  
  
### <a name="to-create-the-loan-class"></a>Создание класса Loan  
  
1. Создайте проект библиотеки классов и назовите его LoanClass. Дополнительные сведения см. в разделе [Создание проектов и решений](https://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects).  
  
2. В **обозревателе решений** щелкните правой кнопкой мыши файл Class1 и выберите команду **Переименовать**. Измените имя файла на `Loan` и нажмите клавишу ВВОД. При переименовании файла класс также будет переименован в `Loan`.  
  
3. Добавьте в класс следующие открытые члены:  
  
    ```vb  
    Public Class Loan  
        Implements System.ComponentModel.INotifyPropertyChanged  
  
        Public Property LoanAmount As Double  
        Public Property InterestRate As Double  
        Public Property Term As Integer  
  
        Private p_Customer As String  
        Public Property Customer As String  
            Get  
                Return p_Customer  
            End Get  
            Set(ByVal value As String)  
                p_Customer = value  
                RaiseEvent PropertyChanged(Me,  
                  New System.ComponentModel.PropertyChangedEventArgs("Customer"))  
            End Set  
        End Property  
  
        Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
          Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
  
        Public Sub New(ByVal loanAmount As Double,  
                       ByVal interestRate As Double,  
                       ByVal term As Integer,  
                       ByVal customer As String)  
  
            Me.LoanAmount = loanAmount  
            Me.InterestRate = interestRate  
            Me.Term = term  
            p_Customer = customer  
        End Sub  
    End Class  
    ```  
  
 Также потребуется создать простое приложение, которое использует класс `Loan`.  
  
### <a name="to-create-a-test-application"></a>Создание тестового приложения  
  
1. Чтобы добавить проект приложения Windows Forms в существующее решение, щелкните в меню **Файл** пункт **Добавить**, а затем **Новый проект**.  
  
2. В диалоговом окне **Добавление нового проекта** выберите **Приложение Windows Forms** и введите `LoanApp` в качестве имени проекта, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
3. В **обозревателе решений** выберите проект LoanApp.  
  
4. В меню **Проект** выберите команду **Назначить запускаемым проектом**.  
  
5. В меню **Проект** выберите **Добавить ссылку**.  
  
6. В диалоговом окне **Добавление ссылки** откройте вкладку **Проекты** и выберите проект LoanClass.  
  
7. Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.  
  
8. В конструкторе добавьте на форму четыре элемента управления <xref:System.Windows.Forms.TextBox>.  
  
9. В редакторе кода добавьте следующий код:  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
10. Добавьте в форму обработчик события для события `PropertyChanged`, воспользовавшись следующим кодом:  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 Теперь можно собрать и запустить приложение. Обратите внимание, что в текстовых полях отображаются значения по умолчанию из класса `Loan`. Попробуйте изменить значение процентной ставки с 7,5 на 7,1, затем закройте приложение и запустите его снова — будет восстановлено заданное по умолчанию значение 7,5.  
  
 В реальной жизни процентная ставка время от времени меняется, но не при каждом запуске этого приложения. Чтобы не заставлять пользователя обновлять процентную ставку при каждом запуске приложения, рекомендуется сохранять самое последнее значение процентной ставки между экземплярами приложения. На следующем шаге для этого в класс Loan будет добавлена сериализация.  
  
## <a name="using-serialization-to-persist-the-object"></a>Использование сериализации для хранения объекта  
 Чтобы сохранить значения для класса Loan, прежде всего необходимо отметить класс атрибутом `Serializable`.  
  
### <a name="to-mark-a-class-as-serializable"></a>Отметка класса как сериализуемого  
  
- Измените объявление класса для класса Loan следующим образом:  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 Атрибут `Serializable` сообщает компилятору, что все находящееся в классе может быть сохранено в файле. Поскольку событие `PropertyChanged` обрабатывается в объекте Windows Form, его невозможно сериализовать. Атрибут `NonSerialized` используется для пометки членов класса, которые не следует сохранять.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>Предотвращение сериализации членов  
  
- Измените объявление события `PropertyChanged` следующим образом:  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 Следующим шагом будет добавление кода сериализации в приложение LoanApp. Чтобы выполнить сериализацию класса и записать данные в файл, используйте пространства имен <xref:System.IO> и <xref:System.Xml.Serialization>. Во избежание ввода полных имен можно добавить ссылки на необходимые библиотеки классов.  
  
### <a name="to-add-references-to-namespaces"></a>Добавление ссылок на пространства имен  
  
- Добавьте в начало файла `Form1` следующие инструкции:  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     В этом случае используется двоичный модуль форматирования для сохранения объекта в двоичном формате.  
  
 Следующим шагом является добавление кода для десериализации объекта из файла при создании объекта.  
  
### <a name="to-deserialize-an-object"></a>Десериализация объекта  
  
1. Добавьте в класс константу для имени файла сериализованных данных.  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2. Измените код процедуры события `Form1_Load` следующим образом:  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        If File.Exists(FileName) Then  
            Dim TestFileStream As Stream = File.OpenRead(FileName)  
            Dim deserializer As New BinaryFormatter  
            TestLoan = CType(deserializer.Deserialize(TestFileStream), LoanClass.Loan)  
            TestFileStream.Close()  
        End If  
  
        AddHandler TestLoan.PropertyChanged, AddressOf Me.CustomerPropertyChanged  
  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
     Прежде всего убедитесь, что файл существует. Если он существует, создайте класс <xref:System.IO.Stream> для чтения двоичного файла и класс <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> для преобразования файла. Кроме того, необходимо преобразовать тип потока в тип объекта Loan.  
  
 Далее необходимо добавить код для сохранения данных, введенных в текстовые поля класса `Loan`, а затем сериализовать класс в файл.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>Сохранение данных и сериализация класса  
  
- В процедуру события `Form1_FormClosing` добавьте следующий код:  
  
    ```vb  
    Private Sub Form1_FormClosing() Handles MyBase.FormClosing  
        TestLoan.LoanAmount = CDbl(TextBox1.Text)  
        TestLoan.InterestRate = CDbl(TextBox2.Text)  
        TestLoan.Term = CInt(TextBox3.Text)  
        TestLoan.Customer = TextBox4.Text  
  
        Dim TestFileStream As Stream = File.Create(FileName)  
        Dim serializer As New BinaryFormatter  
        serializer.Serialize(TestFileStream, TestLoan)  
        TestFileStream.Close()  
    End Sub  
    ```  
  
 Теперь можно снова собрать и запустить приложение. Первоначально в текстовых полях отображаются значения по умолчанию. Попробуйте изменить их и ввести имя в четвертое текстовое поле. Закройте приложение, а затем снова запустите его. Обратите внимание, что теперь в текстовых полях отображаются новые значения.  
  
## <a name="see-also"></a>См. также

- [Сериализация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)

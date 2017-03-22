---
title: "Сохранение объекта в Visual Studio (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0ff6320aee65850b8b445f445f80b4bbe2c9c254
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a>Пошаговое руководство: Сохранение объекта в Visual Studio (Visual Basic)
Несмотря на то, что во время разработки, можно задать свойства объекта значения по умолчанию, любые значения, введенные во время выполнения будут потеряны при уничтожении объекта. Сериализацию можно использовать для сохранения данных объекта между экземплярами, что позволяет сохранять значения и извлекать их при следующем обновлении экземпляра объекта.  
  
> [!NOTE]
>  В Visual Basic для хранения простых данных, таких как имя или число, можно использовать `My.Settings` объекта. Дополнительные сведения см. в разделе [My.Settings-объект](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
 В этом пошаговом руководстве будет создан простой `Loan` объекта и сохранения его данных в файл. Затем будет получать данные из файла, при повторном создании объекта.  
  
> [!IMPORTANT]
>  В этом примере создается новый файл, если файл еще не существует. Если приложение должно создать файл, то ему необходимо `Create` разрешения для папки. Настройка разрешений выполняется с помощью списков управления доступом. Если файл уже существует, приложению требуется только `Write` разрешение, меньшее разрешение. Там, где это возможно, безопаснее создать файл во время развертывания и предоставить `Read` разрешения для одного файла (вместо создания разрешений для папки). Кроме того он является более безопасным для записи данных в пользовательские папки, а в корневом каталоге или каталоге Program Files.  
  
> [!IMPORTANT]
>  В этом примере хранит данные в двоичном файле. Эти форматы не должен использоваться для конфиденциальных данных, таких как пароли или сведения о кредитной карте.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-loan-object"></a>Создание объекта Loan  
 Первым шагом является создание `Loan` класс и тестовое приложение, которое использует класс.  
  
### <a name="to-create-the-loan-class"></a>Чтобы создать класс Loan  
  
1.  Создайте новый проект библиотеки классов и назовите его «LoanClass». Дополнительные сведения см. в разделе [Создание проектов и решений](http://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects).  
  
2.  В **обозревателе решений**, откройте контекстное меню для файла Class1 и выберите **переименование**. Переименуйте файл `Loan` и нажмите клавишу ВВОД. Переименование файла также Переименуйте класс в `Loan`.  
  
3.  Добавьте в класс следующие открытые члены:  
  
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
  
 Также нужно будет создать простое приложение, которое использует `Loan` класса.  
  
### <a name="to-create-a-test-application"></a>Создание тестового приложения  
  
1.  Чтобы добавить решение, проект приложения Windows Forms на **файл** меню, выберите **добавить**,**новый проект**.  
  
2.  В **Добавление нового проекта** диалогового окна выберите **приложение Windows Forms**и введите `LoanApp` как имя проекта и нажмите кнопку **ОК** чтобы закрыть диалоговое окно.  
  
3.  В **обозревателе**, выберите проект LoanApp.  
  
4.  На **проекта** меню, выберите **Назначить запускаемым проектом**.  
  
5.  В меню **Проект** выберите **Добавить ссылку**.  
  
6.  В **добавить ссылку** диалогового окна выберите **проекты** вкладку и выберите проект LoanClass.  
  
7.  Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.  
  
8.  В конструкторе добавьте четыре <xref:System.Windows.Forms.TextBox>элементов управления в форме.</xref:System.Windows.Forms.TextBox>  
  
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
  
10. Добавьте обработчик событий для `PropertyChanged` в форму, используя следующий код:  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 На этом этапе можно построить и запустить приложение. Обратите внимание, что значения по умолчанию из `Loan` класс отображается в текстовых полях. Попробуйте изменить значение процентной ставки с 7,5 на 7.1, закройте приложение и запустите его снова, возвращается значение по умолчанию 7.5.  
  
 В реальном мире интерес изменении ставок, но не при каждом запуске приложения. Вместо того чтобы заставлять пользователя обновлять процентную ставку при каждом запуске приложения, рекомендуется сохранять самые последние процентной ставки между экземплярами приложения. На следующем шаге будет сделать это, добавив сериализации класса Loan.  
  
## <a name="using-serialization-to-persist-the-object"></a>Использование сериализации для хранения объекта  
 Чтобы сохранить значения для класса Loan, необходимо пометить класс `Serializable` атрибута.  
  
### <a name="to-mark-a-class-as-serializable"></a>Чтобы пометить класс как сериализуемый  
  
-   Измените объявление класса для класса Loan следующим образом:  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 `Serializable` Атрибут сообщает компилятору, что все, что в классе может быть сохранено в файл. Поскольку `PropertyChanged` событие обрабатывается в объекте Windows Form, его невозможно сериализовать. `NonSerialized` Атрибут можно использовать для пометки членов класса, которые не следует сохранять.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>Чтобы предотвратить сериализацию члена  
  
-   Измените объявление `PropertyChanged` событие следующим образом:  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 Следующим шагом является добавление кода сериализации в приложение LoanApp. Для сериализации класса и записи в файл, будут использовать <xref:System.IO>и <xref:System.Xml.Serialization>пространства имен.</xref:System.Xml.Serialization> </xref:System.IO> Во избежание ввода полных имен, можно добавить ссылки на необходимые библиотеки классов.  
  
### <a name="to-add-references-to-namespaces"></a>Добавьте ссылки на пространства имен  
  
-   Добавьте следующие операторы в верхнюю часть `Form1` класса:  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     В этом случае используется двоичный модуль форматирования для сохранения объекта в двоичном формате.  
  
 Следующим шагом является добавление кода десериализации объекта из файла при создании объекта.  
  
### <a name="to-deserialize-an-object"></a>Десериализация объекта  
  
1.  Добавьте в класс для имени файла сериализованных данных константу.  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2.  Измените код в `Form1_Load` процедуру события следующим образом:  
  
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
  
     Обратите внимание, что прежде всего убедитесь, что файл существует. Если он существует, создайте <xref:System.IO.Stream>класс для чтения двоичного файла и <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>класс для преобразования файла.</xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> </xref:System.IO.Stream> Необходимо также выполнить преобразование из типа потока в тип объекта Loan.  
  
 Далее необходимо добавить код для сохранения данных, введенных в текстовые поля для `Loan` класса, а затем сериализовать класс в файл.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>Чтобы сохранить данные и сериализовать класс  
  
-   Добавьте следующий код в `Form1_FormClosing` процедуру обработки события:  
  
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
  
 На этом этапе можно снова Постройте и запустите приложение. Первоначально в текстовых полях отображаются значения по умолчанию. Попробуйте изменить значения и введите имя в четвертое текстовое поле. Закройте приложение и запустите его снова. Обратите внимание, что теперь отображаются новые значения в текстовых полях.  
  
## <a name="see-also"></a>См. также  
 [Сериализация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)   
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)

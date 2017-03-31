---
title: "Пошаговое руководство. Сохранение объекта в Visual Studio (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: a544ce46-ee25-49da-afd4-457a3d59bf63
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f76e40e2503bf857922490d728c3a9f3432aa31f
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-persisting-an-object-in-visual-studio-c"></a>Пошаговое руководство. Сохранение объекта в Visual Studio (C#)
Несмотря на то, что во время разработки свойствам объекта можно задать значения по умолчанию, любые значения, введенные во время выполнения, будут потеряны при уничтожении объекта. С помощью сериализации можно сохранить данные объекта между экземплярами, что позволит сохранять значения и извлекать их при следующем создании экземпляра объекта.  
  
 В этом пошаговом руководстве будет создан простой объект `Loan`, а его данные сохранены в файл. Затем при повторном создании объекта вы получите данные из файла.  
  
> [!IMPORTANT]
>  В этом примере создается файл (если файл отсутствует). Если приложение должно создать файл, ему необходимо разрешение `Create` для папки. Для задания разрешений используются списки управления доступом. Если файл уже существует, приложению требуется лишь разрешение `Write` (с более низким уровнем). Если возможно, безопаснее создать файл во время развертывания и предоставить только разрешение `Read` для одного файла (вместо разрешения Create для папки). По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в коревую папку или папку Program Files.  
  
> [!IMPORTANT]
>  В этом примере данные сохраняются в двоичном формате. Эти форматы не следует использовать для конфиденциальных данных, таких как пароли или сведения о кредитных картах.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-loan-object"></a>Создание объекта Loan  
 Первым шагом является создание класса `Loan` и тестового приложения, которое использует класс.  
  
### <a name="to-create-the-loan-class"></a>Создание класса Loan  
  
1.  Создайте проект библиотеки классов и назовите его LoanClass. Дополнительные сведения см. в разделе [Создание проектов и решений](https://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects).  
  
2.  В **обозревателе решений** щелкните правой кнопкой мыши файл Class1 и выберите команду **Переименовать**. Измените имя файла на `Loan` и нажмите клавишу ВВОД. При переименовании файла класс также будет переименован в `Loan`.  
  
3.  Добавьте в класс следующие открытые члены:  
  
    ```csharp  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
        public double LoanAmount {get; set;}  
        public double InterestRate {get; set;}  
        public int Term {get; set;}  
  
        private string p_Customer;  
        public string Customer  
        {  
            get { return p_Customer; }  
            set   
            {  
                p_Customer = value;  
                PropertyChanged(this,  
                  new System.ComponentModel.PropertyChangedEventArgs("Customer"));  
            }  
        }  
  
        public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
  
        public Loan(double loanAmount,  
                    double interestRate,  
                    int term,  
                    string customer)  
        {  
            this.LoanAmount = loanAmount;  
            this.InterestRate = interestRate;  
            this.Term = term;  
            p_Customer = customer;  
        }  
    }  
    ```  
  
 Также потребуется создать простое приложение, которое использует класс `Loan`.  
  
### <a name="to-create-a-test-application"></a>Создание тестового приложения  
  
1.  Чтобы добавить решение проект приложения Windows Forms, в меню **Файл** выберите пункт **Добавить**, а затем щелкните **Новый проект**.  
  
2.  В диалоговом окне **Добавление нового проекта** выберите **Приложение Windows Forms** и введите `LoanApp` в качестве имени проекта, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
3.  В **обозревателе решений** выберите проект LoanApp.  
  
4.  В меню **Проект**выберите команду **Назначить запускаемым проектом**.  
  
5.  В меню **Проект** выберите **Добавить ссылку**.  
  
6.  В диалоговом окне **Добавление ссылки** откройте вкладку **Проекты** и выберите проект LoanClass.  
  
7.  Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.  
  
8.  В конструкторе добавьте в форму четыре элемента управления <xref:System.Windows.Forms.TextBox>.  
  
9. В редакторе кода добавьте следующий код:  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
10. Добавьте в форму обработчик события для события `PropertyChanged`, воспользовавшись следующим кодом:  
  
    ```csharp  
    private void CustomerPropertyChanged(object sender,   
        System.ComponentModel.PropertyChangedEventArgs e)  
    {  
        MessageBox.Show(e.PropertyName + " has been changed.");  
    }  
    ```  
  
 Теперь можно собрать и запустить приложение. Обратите внимание, что в текстовых полях отображаются значения по умолчанию из класса `Loan`. Попробуйте изменить значение процентной ставки с 7,5 на 7,1, затем закройте приложение и запустите его снова — будет восстановлено заданное по умолчанию значение 7,5.  
  
 В реальной жизни процентная ставка время от времени меняется, но не при каждом запуске этого приложения. Чтобы не заставлять пользователя обновлять процентную ставку при каждом запуске приложения, рекомендуется сохранять самое последнее значение процентной ставки между экземплярами приложения. На следующем шаге для этого в класс Loan будет добавлена сериализация.  
  
## <a name="using-serialization-to-persist-the-object"></a>Использование сериализации для хранения объекта  
 Чтобы сохранить значения для класса Loan, прежде всего необходимо отметить класс атрибутом `Serializable`.  
  
### <a name="to-mark-a-class-as-serializable"></a>Отметка класса как сериализуемого  
  
-   Измените объявление класса для класса Loan следующим образом:  
  
    ```csharp  
    [Serializable()]  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
    ```  
  
 Атрибут `Serializable` сообщает компилятору, что все находящееся в классе может быть сохранено в файле. Поскольку событие `PropertyChanged` обрабатывается в объекте Windows Form, его невозможно сериализовать. Атрибут `NonSerialized` используется для пометки членов класса, которые не следует сохранять.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>Предотвращение сериализации членов  
  
-   Измените объявление события `PropertyChanged` следующим образом:  
  
    ```csharp  
    [field: NonSerialized()]  
    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
    ```  
  
 Следующим шагом будет добавление кода сериализации в приложение LoanApp. Для сериализации класса и записи в файл следует использовать пространства имен <xref:System.IO> и <xref:System.Xml.Serialization>. Во избежание ввода полных имен можно добавить ссылки на необходимые библиотеки классов.  
  
### <a name="to-add-references-to-namespaces"></a>Добавление ссылок на пространства имен  
  
-   Добавьте в начало файла `Form1` следующие инструкции:  
  
    ```csharp  
    using System.IO;  
    using System.Runtime.Serialization.Formatters.Binary;  
    ```  
  
     В этом случае используется двоичный модуль форматирования для сохранения объекта в двоичном формате.  
  
 Следующим шагом является добавление кода для десериализации объекта из файла при создании объекта.  
  
### <a name="to-deserialize-an-object"></a>Десериализация объекта  
  
1.  Добавьте в класс константу для имени файла сериализованных данных.  
  
    ```csharp  
    const string FileName = @"..\..\SavedLoan.bin";  
    ```  
  
2.  Измените код процедуры события `Form1_Load` следующим образом:  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        if (File.Exists(FileName))  
        {  
            Stream TestFileStream = File.OpenRead(FileName);  
            BinaryFormatter deserializer = new BinaryFormatter();  
            TestLoan = (LoanClass.Loan)deserializer.Deserialize(TestFileStream);  
            TestFileStream.Close();  
        }  
  
        TestLoan.PropertyChanged += this.CustomerPropertyChanged;  
  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
     Прежде всего убедитесь, что файл существует. Если он существует, создайте класс <xref:System.IO.Stream> для чтения двоичного файла и класс <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> для преобразования файла. Кроме того, необходимо преобразовать тип потока в тип объекта Loan.  
  
 Далее необходимо добавить код для сохранения данных, введенных в текстовые поля класса `Loan`, а затем сериализовать класс в файл.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>Сохранение данных и сериализация класса  
  
-   В процедуру события `Form1_FormClosing` добавьте следующий код:  
  
    ```csharp  
    private void Form1_FormClosing(object sender, FormClosingEventArgs e)  
    {  
        TestLoan.LoanAmount = Convert.ToDouble(textBox1.Text);  
        TestLoan.InterestRate = Convert.ToDouble(textBox2.Text);  
        TestLoan.Term = Convert.ToInt32(textBox3.Text);  
        TestLoan.Customer = textBox4.Text;  
  
        Stream TestFileStream = File.Create(FileName);  
        BinaryFormatter serializer = new BinaryFormatter();  
        serializer.Serialize(TestFileStream, TestLoan);  
        TestFileStream.Close();  
    }  
    ```  
  
 Теперь можно снова собрать и запустить приложение. Первоначально в текстовых полях отображаются значения по умолчанию. Попробуйте изменить их и ввести имя в четвертое текстовое поле. Закройте приложение, а затем снова запустите его. Обратите внимание, что теперь в текстовых полях отображаются новые значения.  
  
## <a name="see-also"></a>См. также  
 [Сериализация (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md)   
 [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)


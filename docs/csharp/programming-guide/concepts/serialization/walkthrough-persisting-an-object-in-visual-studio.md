---
title: "Пошаговое руководство. Сохранение объекта в Visual Studio (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: get-started-article
ms.assetid: a544ce46-ee25-49da-afd4-457a3d59bf63
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b1a3fc377875ee25baa0718a25b5ac509822154
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-c"></a><span data-ttu-id="274b6-102">Пошаговое руководство. Сохранение объекта в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="274b6-102">Walkthrough: Persisting an Object in Visual Studio (C#)</span></span>
<span data-ttu-id="274b6-103">Несмотря на то, что во время разработки свойствам объекта можно задать значения по умолчанию, любые значения, введенные во время выполнения, будут потеряны при уничтожении объекта.</span><span class="sxs-lookup"><span data-stu-id="274b6-103">Although you can set an object's properties to default values at design time, any values entered at run time are lost when the object is destroyed.</span></span> <span data-ttu-id="274b6-104">С помощью сериализации можно сохранить данные объекта между экземплярами, что позволит сохранять значения и извлекать их при следующем создании экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="274b6-104">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>  
  
 <span data-ttu-id="274b6-105">В этом пошаговом руководстве будет создан простой объект `Loan`, а его данные сохранены в файл.</span><span class="sxs-lookup"><span data-stu-id="274b6-105">In this walkthrough, you will create a simple `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="274b6-106">Затем при повторном создании объекта вы получите данные из файла.</span><span class="sxs-lookup"><span data-stu-id="274b6-106">You will then retrieve the data from the file when you re-create the object.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="274b6-107">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="274b6-107">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="274b6-108">Если приложение должно создать файл, ему необходимо разрешение `Create` для папки.</span><span class="sxs-lookup"><span data-stu-id="274b6-108">If an application must create a file, that application must `Create` permission for the folder.</span></span> <span data-ttu-id="274b6-109">Для задания разрешений используются списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="274b6-109">Permissions are set by using access control lists.</span></span> <span data-ttu-id="274b6-110">Если файл уже существует, приложению требуется лишь разрешение `Write` (с более низким уровнем).</span><span class="sxs-lookup"><span data-stu-id="274b6-110">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="274b6-111">Если возможно, безопаснее создать файл во время развертывания и предоставить только разрешение `Read` для одного файла (вместо разрешения Create для папки).</span><span class="sxs-lookup"><span data-stu-id="274b6-111">Where possible, it is more secure to create the file during deployment, and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="274b6-112">По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в коревую папку или папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="274b6-112">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="274b6-113">В этом примере данные сохраняются в двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="274b6-113">This example stores data in a binary format file.</span></span> <span data-ttu-id="274b6-114">Эти форматы не следует использовать для конфиденциальных данных, таких как пароли или сведения о кредитных картах.</span><span class="sxs-lookup"><span data-stu-id="274b6-114">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="274b6-115">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="274b6-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="274b6-116">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="274b6-116">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="274b6-117">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="274b6-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-loan-object"></a><span data-ttu-id="274b6-118">Создание объекта Loan</span><span class="sxs-lookup"><span data-stu-id="274b6-118">Creating the Loan Object</span></span>  
 <span data-ttu-id="274b6-119">Первым шагом является создание класса `Loan` и тестового приложения, которое использует класс.</span><span class="sxs-lookup"><span data-stu-id="274b6-119">The first step is to create a `Loan` class and a test application that uses the class.</span></span>  
  
### <a name="to-create-the-loan-class"></a><span data-ttu-id="274b6-120">Создание класса Loan</span><span class="sxs-lookup"><span data-stu-id="274b6-120">To create the Loan class</span></span>  
  
1.  <span data-ttu-id="274b6-121">Создайте проект библиотеки классов и назовите его LoanClass.</span><span class="sxs-lookup"><span data-stu-id="274b6-121">Create a new Class Library project and name it "LoanClass".</span></span> <span data-ttu-id="274b6-122">Дополнительные сведения см. в разделе [Создание проектов и решений](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="274b6-122">For more information, see [Creating Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).</span></span>  
  
2.  <span data-ttu-id="274b6-123">В **обозревателе решений** щелкните правой кнопкой мыши файл Class1 и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="274b6-123">In **Solution Explorer**, open the shortcut menu for the Class1 file and choose **Rename**.</span></span> <span data-ttu-id="274b6-124">Измените имя файла на `Loan` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="274b6-124">Rename the file to `Loan` and press ENTER.</span></span> <span data-ttu-id="274b6-125">При переименовании файла класс также будет переименован в `Loan`.</span><span class="sxs-lookup"><span data-stu-id="274b6-125">Renaming the file will also rename the class to `Loan`.</span></span>  
  
3.  <span data-ttu-id="274b6-126">Добавьте в класс следующие открытые члены:</span><span class="sxs-lookup"><span data-stu-id="274b6-126">Add the following public members to the class:</span></span>  
  
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
  
 <span data-ttu-id="274b6-127">Также потребуется создать простое приложение, которое использует класс `Loan`.</span><span class="sxs-lookup"><span data-stu-id="274b6-127">You will also have to create a simple application that uses the `Loan` class.</span></span>  
  
### <a name="to-create-a-test-application"></a><span data-ttu-id="274b6-128">Создание тестового приложения</span><span class="sxs-lookup"><span data-stu-id="274b6-128">To create a test application</span></span>  
  
1.  <span data-ttu-id="274b6-129">Чтобы добавить решение проект приложения Windows Forms, в меню **Файл** выберите пункт **Добавить**, а затем щелкните **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="274b6-129">To add a Windows Forms Application project to your solution, on the **File** menu, choose **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="274b6-130">В диалоговом окне **Добавление нового проекта** выберите **Приложение Windows Forms** и введите `LoanApp` в качестве имени проекта, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="274b6-130">In the **Add New Project** dialog box, choose **Windows Forms Application**, and enter `LoanApp` as the name of the project, and then click **OK** to close the dialog box.</span></span>  
  
3.  <span data-ttu-id="274b6-131">В **обозревателе решений** выберите проект LoanApp.</span><span class="sxs-lookup"><span data-stu-id="274b6-131">In **Solution Explorer**, choose the LoanApp project.</span></span>  
  
4.  <span data-ttu-id="274b6-132">В меню **Проект** выберите команду **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="274b6-132">On the **Project** menu, choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="274b6-133">В меню **Проект** выберите **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="274b6-133">On the **Project** menu, choose **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="274b6-134">В диалоговом окне **Добавление ссылки** откройте вкладку **Проекты** и выберите проект LoanClass.</span><span class="sxs-lookup"><span data-stu-id="274b6-134">In the **Add Reference** dialog box, choose the **Projects** tab and then choose the LoanClass project.</span></span>  
  
7.  <span data-ttu-id="274b6-135">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="274b6-135">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="274b6-136">В конструкторе добавьте на форму четыре элемента управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="274b6-136">In the designer, add four <xref:System.Windows.Forms.TextBox> controls to the form.</span></span>  
  
9. <span data-ttu-id="274b6-137">В редакторе кода добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="274b6-137">In the Code Editor, add the following code:</span></span>  
  
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
  
10. <span data-ttu-id="274b6-138">Добавьте в форму обработчик события для события `PropertyChanged`, воспользовавшись следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="274b6-138">Add an event handler for the `PropertyChanged` event to the form by using the following code:</span></span>  
  
    ```csharp  
    private void CustomerPropertyChanged(object sender,   
        System.ComponentModel.PropertyChangedEventArgs e)  
    {  
        MessageBox.Show(e.PropertyName + " has been changed.");  
    }  
    ```  
  
 <span data-ttu-id="274b6-139">Теперь можно собрать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="274b6-139">At this point, you can build and run the application.</span></span> <span data-ttu-id="274b6-140">Обратите внимание, что в текстовых полях отображаются значения по умолчанию из класса `Loan`.</span><span class="sxs-lookup"><span data-stu-id="274b6-140">Note that the default values from the `Loan` class appear in the text boxes.</span></span> <span data-ttu-id="274b6-141">Попробуйте изменить значение процентной ставки с 7,5 на 7,1, затем закройте приложение и запустите его снова — будет восстановлено заданное по умолчанию значение 7,5.</span><span class="sxs-lookup"><span data-stu-id="274b6-141">Try to change the interest-rate value from 7.5 to 7.1, and then close the application and run it again—the value reverts to the default of 7.5.</span></span>  
  
 <span data-ttu-id="274b6-142">В реальной жизни процентная ставка время от времени меняется, но не при каждом запуске этого приложения.</span><span class="sxs-lookup"><span data-stu-id="274b6-142">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="274b6-143">Чтобы не заставлять пользователя обновлять процентную ставку при каждом запуске приложения, рекомендуется сохранять самое последнее значение процентной ставки между экземплярами приложения.</span><span class="sxs-lookup"><span data-stu-id="274b6-143">Rather than making the user update the interest rate every time that the application runs, it is better to preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="274b6-144">На следующем шаге для этого в класс Loan будет добавлена сериализация.</span><span class="sxs-lookup"><span data-stu-id="274b6-144">In the next step, you will do just that by adding serialization to the Loan class.</span></span>  
  
## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="274b6-145">Использование сериализации для хранения объекта</span><span class="sxs-lookup"><span data-stu-id="274b6-145">Using Serialization to Persist the Object</span></span>  
 <span data-ttu-id="274b6-146">Чтобы сохранить значения для класса Loan, прежде всего необходимо отметить класс атрибутом `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="274b6-146">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span>  
  
### <a name="to-mark-a-class-as-serializable"></a><span data-ttu-id="274b6-147">Отметка класса как сериализуемого</span><span class="sxs-lookup"><span data-stu-id="274b6-147">To mark a class as serializable</span></span>  
  
-   <span data-ttu-id="274b6-148">Измените объявление класса для класса Loan следующим образом:</span><span class="sxs-lookup"><span data-stu-id="274b6-148">Change the class declaration for the Loan class as follows:</span></span>  
  
    ```csharp  
    [Serializable()]  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
    ```  
  
 <span data-ttu-id="274b6-149">Атрибут `Serializable` сообщает компилятору, что все находящееся в классе может быть сохранено в файле.</span><span class="sxs-lookup"><span data-stu-id="274b6-149">The `Serializable` attribute tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="274b6-150">Поскольку событие `PropertyChanged` обрабатывается в объекте Windows Form, его невозможно сериализовать.</span><span class="sxs-lookup"><span data-stu-id="274b6-150">Because the `PropertyChanged` event is handled by a Windows Form object, it cannot be serialized.</span></span> <span data-ttu-id="274b6-151">Атрибут `NonSerialized` используется для пометки членов класса, которые не следует сохранять.</span><span class="sxs-lookup"><span data-stu-id="274b6-151">The `NonSerialized` attribute can be used to mark class members that should not be persisted.</span></span>  
  
### <a name="to-prevent-a-member-from-being-serialized"></a><span data-ttu-id="274b6-152">Предотвращение сериализации членов</span><span class="sxs-lookup"><span data-stu-id="274b6-152">To prevent a member from being serialized</span></span>  
  
-   <span data-ttu-id="274b6-153">Измените объявление события `PropertyChanged` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="274b6-153">Change the declaration for the `PropertyChanged` event as follows:</span></span>  
  
    ```csharp  
    [field: NonSerialized()]  
    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
    ```  
  
 <span data-ttu-id="274b6-154">Следующим шагом будет добавление кода сериализации в приложение LoanApp.</span><span class="sxs-lookup"><span data-stu-id="274b6-154">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="274b6-155">Чтобы выполнить сериализацию класса и записать данные в файл, используйте пространства имен <xref:System.IO> и <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="274b6-155">In order to serialize the class and write it to a file, you will use the <xref:System.IO> and <xref:System.Xml.Serialization> namespaces.</span></span> <span data-ttu-id="274b6-156">Во избежание ввода полных имен можно добавить ссылки на необходимые библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="274b6-156">To avoid typing the fully qualified names, you can add references to the necessary class libraries.</span></span>  
  
### <a name="to-add-references-to-namespaces"></a><span data-ttu-id="274b6-157">Добавление ссылок на пространства имен</span><span class="sxs-lookup"><span data-stu-id="274b6-157">To add references to namespaces</span></span>  
  
-   <span data-ttu-id="274b6-158">Добавьте в начало файла `Form1` следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="274b6-158">Add the following statements to the top of the `Form1` class:</span></span>  
  
    ```csharp  
    using System.IO;  
    using System.Runtime.Serialization.Formatters.Binary;  
    ```  
  
     <span data-ttu-id="274b6-159">В этом случае используется двоичный модуль форматирования для сохранения объекта в двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="274b6-159">In this case, you are using a binary formatter to save the object in a binary format.</span></span>  
  
 <span data-ttu-id="274b6-160">Следующим шагом является добавление кода для десериализации объекта из файла при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="274b6-160">The next step is to add code to deserialize the object from the file when the object is created.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="274b6-161">Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="274b6-161">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="274b6-162">Добавьте в класс константу для имени файла сериализованных данных.</span><span class="sxs-lookup"><span data-stu-id="274b6-162">Add a constant to the class for the serialized data's file name.</span></span>  
  
    ```csharp  
    const string FileName = @"..\..\SavedLoan.bin";  
    ```  
  
2.  <span data-ttu-id="274b6-163">Измените код процедуры события `Form1_Load` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="274b6-163">Modify the code in the `Form1_Load` event procedure as follows:</span></span>  
  
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
  
     <span data-ttu-id="274b6-164">Прежде всего убедитесь, что файл существует.</span><span class="sxs-lookup"><span data-stu-id="274b6-164">Note that you first must check that the file exists.</span></span> <span data-ttu-id="274b6-165">Если он существует, создайте класс <xref:System.IO.Stream> для чтения двоичного файла и класс <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> для преобразования файла.</span><span class="sxs-lookup"><span data-stu-id="274b6-165">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="274b6-166">Кроме того, необходимо преобразовать тип потока в тип объекта Loan.</span><span class="sxs-lookup"><span data-stu-id="274b6-166">You also need to convert from the stream type to the Loan object type.</span></span>  
  
 <span data-ttu-id="274b6-167">Далее необходимо добавить код для сохранения данных, введенных в текстовые поля класса `Loan`, а затем сериализовать класс в файл.</span><span class="sxs-lookup"><span data-stu-id="274b6-167">Next you must add code to save the data entered in the text boxes to the `Loan` class, and then you must serialize the class to a file.</span></span>  
  
### <a name="to-save-the-data-and-serialize-the-class"></a><span data-ttu-id="274b6-168">Сохранение данных и сериализация класса</span><span class="sxs-lookup"><span data-stu-id="274b6-168">To save the data and serialize the class</span></span>  
  
-   <span data-ttu-id="274b6-169">В процедуру события `Form1_FormClosing` добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="274b6-169">Add the following code to the `Form1_FormClosing` event procedure:</span></span>  
  
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
  
 <span data-ttu-id="274b6-170">Теперь можно снова собрать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="274b6-170">At this point, you can again build and run the application.</span></span> <span data-ttu-id="274b6-171">Первоначально в текстовых полях отображаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="274b6-171">Initially, the default values appear in the text boxes.</span></span> <span data-ttu-id="274b6-172">Попробуйте изменить их и ввести имя в четвертое текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="274b6-172">Try to change the values and enter a name in the fourth text box.</span></span> <span data-ttu-id="274b6-173">Закройте приложение, а затем снова запустите его.</span><span class="sxs-lookup"><span data-stu-id="274b6-173">Close the application and then run it again.</span></span> <span data-ttu-id="274b6-174">Обратите внимание, что теперь в текстовых полях отображаются новые значения.</span><span class="sxs-lookup"><span data-stu-id="274b6-174">Note that the new values now appear in the text boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="274b6-175">См. также</span><span class="sxs-lookup"><span data-stu-id="274b6-175">See Also</span></span>  
 [<span data-ttu-id="274b6-176">Сериализация (C#)</span><span class="sxs-lookup"><span data-stu-id="274b6-176">Serialization (C# )</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)  
 [<span data-ttu-id="274b6-177">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="274b6-177">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)

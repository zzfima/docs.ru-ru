---
title: Практическое руководство. Связывание данных с элементом управления MaskedTextBox
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8adf445de4648c0a751a852f67a55ca9683e3469
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="70e9a-102">Практическое руководство. Связывание данных с элементом управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="70e9a-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="70e9a-103">Можно привязать данные к <xref:System.Windows.Forms.MaskedTextBox> управления так же, как и любым другим элементом управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="70e9a-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="70e9a-104">Тем не менее если формат данных в базе данных не соответствует формату, ожидаемому определением маски, необходимо будет изменять формат данных.</span><span class="sxs-lookup"><span data-stu-id="70e9a-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="70e9a-105">Ниже показано, как это сделать с помощью <xref:System.Windows.Forms.Binding.Format> и <xref:System.Windows.Forms.Binding.Parse> события <xref:System.Windows.Forms.Binding> класса для отображения отдельных телефон и phone поля расширения базы данных в виде одного поля для редактирования.</span><span class="sxs-lookup"><span data-stu-id="70e9a-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="70e9a-106">Следующая процедура требует наличия доступа к базе данных SQL Server с установленным образца базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="70e9a-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="70e9a-107">Привязка данных к элементу управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="70e9a-107">To bind data to a MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="70e9a-108">Создайте проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="70e9a-108">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="70e9a-109">Перетащите два <xref:System.Windows.Forms.TextBox> элементов управления на форму; присвойте им `FirstName` и `LastName`.</span><span class="sxs-lookup"><span data-stu-id="70e9a-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3.  <span data-ttu-id="70e9a-110">Перетащите <xref:System.Windows.Forms.MaskedTextBox> управления на форму, присвойте ей имя `PhoneMask`.</span><span class="sxs-lookup"><span data-stu-id="70e9a-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4.  <span data-ttu-id="70e9a-111">Задать <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство `PhoneMask` для `(000) 000-0000 x9999`.</span><span class="sxs-lookup"><span data-stu-id="70e9a-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5.  <span data-ttu-id="70e9a-112">Добавьте следующие импорты пространства имен в форму.</span><span class="sxs-lookup"><span data-stu-id="70e9a-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6.  <span data-ttu-id="70e9a-113">Щелкните форму правой кнопкой мыши и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="70e9a-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="70e9a-114">Поместите этот код в любом месте в классе формы.</span><span class="sxs-lookup"><span data-stu-id="70e9a-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the   
        // initial load.   
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the   
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7.  <span data-ttu-id="70e9a-115">Добавьте обработчики событий для <xref:System.Windows.Forms.Binding.Format> и <xref:System.Windows.Forms.Binding.Parse> событий для объединения и разделения `PhoneNumber` и `Extension` поля из границы <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="70e9a-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)   
        {  
            ext = "";  
        } else   
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.   
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.   
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8.  <span data-ttu-id="70e9a-116">Добавление двух <xref:System.Windows.Forms.Button> элементов управления в форму.</span><span class="sxs-lookup"><span data-stu-id="70e9a-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="70e9a-117">Назовите их `previousButton` и `nextButton`.</span><span class="sxs-lookup"><span data-stu-id="70e9a-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="70e9a-118">Дважды щелкните каждую кнопку, чтобы добавить <xref:System.Windows.Forms.Control.Click> обработчик событий и заполните обработчики событий, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="70e9a-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="70e9a-119">Выполните образец.</span><span class="sxs-lookup"><span data-stu-id="70e9a-119">Run the sample.</span></span> <span data-ttu-id="70e9a-120">Измените данные и используйте **Назад** и **Далее** кнопок, чтобы увидеть, что данные правильно сохранены <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="70e9a-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e9a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="70e9a-121">Example</span></span>  
 <span data-ttu-id="70e9a-122">В следующем примере кода приведен полный код, которые являются результатом выполнения описанной процедуры.</span><span class="sxs-lookup"><span data-stu-id="70e9a-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70e9a-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="70e9a-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="70e9a-124">Создание проекта Visual C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="70e9a-124">Create a Visual C# or Visual Basic project.</span></span>  
  
-   <span data-ttu-id="70e9a-125">Добавить <xref:System.Windows.Forms.TextBox> и <xref:System.Windows.Forms.MaskedTextBox> в форму элементы управления, как описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="70e9a-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
-   <span data-ttu-id="70e9a-126">Откройте файл исходного кода для формы по умолчанию проекта.</span><span class="sxs-lookup"><span data-stu-id="70e9a-126">Open the source code file for the project's default form.</span></span>  
  
-   <span data-ttu-id="70e9a-127">Замените исходный код в этот файл код, приведенный в предыдущем разделе «Code».</span><span class="sxs-lookup"><span data-stu-id="70e9a-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
-   <span data-ttu-id="70e9a-128">Скомпилируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="70e9a-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e9a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="70e9a-129">See Also</span></span>  
 [<span data-ttu-id="70e9a-130">Пример. Работа с элементом управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="70e9a-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)

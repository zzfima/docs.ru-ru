---
title: Практическое руководство. Открытие файлов с помощью компонента OpenFileDialog
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
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7da2c660f09da74c84d29459cf283a021ed12c99
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a><span data-ttu-id="57177-102">Практическое руководство. Открытие файлов с помощью компонента OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="57177-102">How to: Open Files Using the OpenFileDialog Component</span></span>
<span data-ttu-id="57177-103"><xref:System.Windows.Forms.OpenFileDialog> Компонент позволяет пользователям просматривать папки на компьютере или на любом компьютере в сети и выбрать один или несколько файлов для открытия.</span><span class="sxs-lookup"><span data-stu-id="57177-103">The <xref:System.Windows.Forms.OpenFileDialog> component allows users to browse the folders of their computer or any computer on the network and select one or more files to open.</span></span> <span data-ttu-id="57177-104">Диалоговое окно возвращает путь и имя файла, который пользователь выбрал в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="57177-104">The dialog box returns the path and name of the file the user selected in the dialog box.</span></span>  
  
 <span data-ttu-id="57177-105">После выбора открываемого файла существует два подхода к открытию файла.</span><span class="sxs-lookup"><span data-stu-id="57177-105">Once the user has selected the file to be opened, there are two approaches to the mechanism of opening the file.</span></span> <span data-ttu-id="57177-106">Если вы предпочитаете работать с потоками файлов, можно создать экземпляр <xref:System.IO.StreamReader> класса.</span><span class="sxs-lookup"><span data-stu-id="57177-106">If you prefer to work with file streams, you can create an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="57177-107">Кроме того, можно использовать <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод, чтобы открыть выбранный файл.</span><span class="sxs-lookup"><span data-stu-id="57177-107">Alternately, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the selected file.</span></span>  
  
 <span data-ttu-id="57177-108">В первом примере включает в себя <xref:System.Security.Permissions.FileIOPermission> проверка разрешений (как описано в «Примечание по безопасности» ниже), но также предоставляет доступ к имени файла.</span><span class="sxs-lookup"><span data-stu-id="57177-108">The first example below involves a <xref:System.Security.Permissions.FileIOPermission> permission check (as described in the "Security Note" below), but gives you access to the filename.</span></span> <span data-ttu-id="57177-109">Этот метод можно использовать из зоны локального компьютера, интрасети и Интернета.</span><span class="sxs-lookup"><span data-stu-id="57177-109">You can use this technique from the Local Machine, Intranet, and Internet zones.</span></span> <span data-ttu-id="57177-110">Второй метод также выполняет <xref:System.Security.Permissions.FileIOPermission> проверку разрешений, но лучше всего подходит для приложений в зоне интрасети или Интернету.</span><span class="sxs-lookup"><span data-stu-id="57177-110">The second method also does a <xref:System.Security.Permissions.FileIOPermission> permission check, but is better suited for applications in the Intranet or Internet zones.</span></span>  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a><span data-ttu-id="57177-111">Открытие файла как потока с помощью компонента OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="57177-111">To open a file as a stream using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="57177-112">Выведите на экран диалоговое окно **Открыть файл** и вызовите метод для открытия файла, выбранного пользователем.</span><span class="sxs-lookup"><span data-stu-id="57177-112">Display the **Open File** dialog box and call a method to open the file selected by the user.</span></span>  
  
     <span data-ttu-id="57177-113">Один подход заключается в использовании <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы открыть диалоговое окно открытия файла и использовать экземпляр <xref:System.IO.StreamReader> класс, чтобы открыть файл.</span><span class="sxs-lookup"><span data-stu-id="57177-113">One approach is to use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the Open File dialog box, and use an instance of the <xref:System.IO.StreamReader> class to open the file.</span></span>  
  
     <span data-ttu-id="57177-114">В приведенном ниже используется <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий, чтобы открыть экземпляр <xref:System.Windows.Forms.OpenFileDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="57177-114">The example below uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open an instance of the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="57177-115">Если файл выбран и пользователь нажимает кнопку **ОК**, открывается файл, выбранный в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="57177-115">When a file is chosen and the user clicks **OK**, the file selected in the dialog box opens.</span></span> <span data-ttu-id="57177-116">В этом случае содержимое отображается в окне сообщения, чтобы показать, что файловый поток считан.</span><span class="sxs-lookup"><span data-stu-id="57177-116">In this case, the contents are displayed in a message box, just to show that the file stream has been read.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="57177-117">Чтобы получить или задать <xref:System.Windows.Forms.FileDialog.FileName%2A> свойства, сборка требует уровня прав доступа предоставляемых по <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="57177-117">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="57177-118">Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий.</span><span class="sxs-lookup"><span data-stu-id="57177-118">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="57177-119">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="57177-119">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="57177-120">В этом примере предполагается, имеет форму <xref:System.Windows.Forms.Button> управления и <xref:System.Windows.Forms.OpenFileDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="57177-120">The example assumes your form has a <xref:System.Windows.Forms.Button> control and an <xref:System.Windows.Forms.OpenFileDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     <span data-ttu-id="57177-121">(Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="57177-121">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="57177-122">Дополнительные сведения о чтении из файлового потока см. в разделе <xref:System.IO.FileStream.BeginRead%2A> и <xref:System.IO.FileStream.Read%2A>.</span><span class="sxs-lookup"><span data-stu-id="57177-122">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A> and <xref:System.IO.FileStream.Read%2A>.</span></span>  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a><span data-ttu-id="57177-123">Открытие файла как файла с помощью компонента OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="57177-123">To open a file as a file using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="57177-124">Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы отобразить диалоговое окно и <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод для открытия файла.</span><span class="sxs-lookup"><span data-stu-id="57177-124">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the file.</span></span>  
  
     <span data-ttu-id="57177-125"><xref:System.Windows.Forms.OpenFileDialog> Компонента <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод возвращает количество байтов, составляющих файл.</span><span class="sxs-lookup"><span data-stu-id="57177-125">The <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method returns the bytes that compose the file.</span></span> <span data-ttu-id="57177-126">Эти байты образуют поток для считывания.</span><span class="sxs-lookup"><span data-stu-id="57177-126">These bytes give you a stream to read from.</span></span> <span data-ttu-id="57177-127">В следующем примере <xref:System.Windows.Forms.OpenFileDialog> экземпляр компонента с фильтром по «курсор»`.cur`.</span><span class="sxs-lookup"><span data-stu-id="57177-127">In the example below, an <xref:System.Windows.Forms.OpenFileDialog> component is instantiated with a "cursor" filter on it, allowing the user to choose only files with the file name extension`.cur`.</span></span> <span data-ttu-id="57177-128">Если выбран файл `.cur`, в качестве курсора формы задается выбранный курсор.</span><span class="sxs-lookup"><span data-stu-id="57177-128">If a`.cur` file is chosen, the form's cursor is set to the selected cursor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="57177-129">Для вызова <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод, сборка требует уровня прав доступа предоставляемых по <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="57177-129">To call the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="57177-130">Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий.</span><span class="sxs-lookup"><span data-stu-id="57177-130">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="57177-131">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="57177-131">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="57177-132">В этом примере предполагается, имеет форму <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="57177-132">The example assumes your form has a <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     <span data-ttu-id="57177-133">(Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="57177-133">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="57177-134">См. также</span><span class="sxs-lookup"><span data-stu-id="57177-134">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="57177-135">Компонент OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="57177-135">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)

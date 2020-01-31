---
title: Более безопасный доступ к файлам и данным
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
ms.openlocfilehash: 49ba1919f68f35e9d72b012540b785e05c307c39
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743749"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="79831-102">Более безопасный доступ к файлам и данным в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79831-102">More Secure File and Data Access in Windows Forms</span></span>
<span data-ttu-id="79831-103">.NET Framework использует разрешения для защиты ресурсов и данных.</span><span class="sxs-lookup"><span data-stu-id="79831-103">The .NET Framework uses permissions to help protect resources and data.</span></span> <span data-ttu-id="79831-104">То, какие данные может считывать или записывать приложение, зависит от предоставленных ему разрешений.</span><span class="sxs-lookup"><span data-stu-id="79831-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="79831-105">Когда приложение работает в среде с частичным доверием, то доступ к данным может быть запрещен или может быть необходимо изменить способ доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="79831-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="79831-106">При возникновении ограничения безопасности есть два варианта: подтверждение разрешения (при условии что оно было предоставлено приложению) или использование версии кода, созданной для работы в режиме частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="79831-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="79831-107">В следующих разделах рассматриваются способы доступа к файлам, базам данных и реестру из приложений, работающих в среде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="79831-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79831-108">По умолчанию средства, создающие развертывания ClickOnce, по умолчанию выполняют эти развертывания для запроса полного доверия от компьютеров, на которых они выполняются.</span><span class="sxs-lookup"><span data-stu-id="79831-108">By default, tools that generate ClickOnce deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="79831-109">Если вы решили использовать новые преимущества безопасности при частичном доверии, необходимо изменить это значение по умолчанию в Visual Studio или в одном из средств Windows SDK (Mage. exe или MageUI. exe).</span><span class="sxs-lookup"><span data-stu-id="79831-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either Visual Studio or one of the Windows SDK tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="79831-110">Дополнительные сведения о безопасности Windows Forms и о том, как определить соответствующий уровень доверия для приложения, см. в статье [Обзор безопасности в Windows Forms](security-in-windows-forms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79831-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="79831-111">Доступ к файлам</span><span class="sxs-lookup"><span data-stu-id="79831-111">File Access</span></span>  
 <span data-ttu-id="79831-112">Класс <xref:System.Security.Permissions.FileIOPermission> управляет доступом к файлам и папкам в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79831-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the .NET Framework.</span></span> <span data-ttu-id="79831-113">По умолчанию система безопасности не предоставляет разрешение <xref:System.Security.Permissions.FileIOPermission> в средах с частичным доверием, таких как зона локальной интрасети или Интернет.</span><span class="sxs-lookup"><span data-stu-id="79831-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="79831-114">Однако приложение, которому требуется доступ к файлам, может работать в таких средах, если изменить структуру приложения или использовать другие методы доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="79831-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="79831-115">По умолчанию зоне локальной интрасети предоставляется право на доступ к тому же сайту и к той же папке, на подключение к исходному сайту и чтение данных из папки установки.</span><span class="sxs-lookup"><span data-stu-id="79831-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="79831-116">Приложениям в зоне Интернета по умолчанию разрешено подключаться только к исходному сайту.</span><span class="sxs-lookup"><span data-stu-id="79831-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="79831-117">Файлы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="79831-117">User-Specified Files</span></span>  
 <span data-ttu-id="79831-118">Один из способов решения проблемы, связанной с отсутствием доступа к файлам, — запросить у пользователя сведения о конкретном файле с помощью объекта <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="79831-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="79831-119">Взаимодействие с пользователем помогает получить некоторую уверенность в том, что приложение не сможет несанкционированно загрузить личные файлы или перезаписать важные файлы.</span><span class="sxs-lookup"><span data-stu-id="79831-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="79831-120">Методы <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> и <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> предоставляют доступ для чтения и записи файла, открывая файловый поток для файла, указанного пользователем.</span><span class="sxs-lookup"><span data-stu-id="79831-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="79831-121">Эти методы также помогают защитить файл пользователя, скрывая путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="79831-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79831-122">Эти разрешения зависят от того, в какой зоне находится приложение: интрасеть или Интернет.</span><span class="sxs-lookup"><span data-stu-id="79831-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="79831-123">Приложения зоны Интернета могут использовать только класс <xref:System.Windows.Forms.OpenFileDialog>, тогда как приложения интрасети имеют неограниченное разрешение на использование файловых диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="79831-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="79831-124">Класс <xref:System.Security.Permissions.FileDialogPermission> указывает, какой тип файлового диалогового окна может использовать приложение.</span><span class="sxs-lookup"><span data-stu-id="79831-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="79831-125">В таблице ниже показаны значения, которые необходимо использовать для каждого класса <xref:System.Windows.Forms.FileDialog>.</span><span class="sxs-lookup"><span data-stu-id="79831-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="79831-126">Класс</span><span class="sxs-lookup"><span data-stu-id="79831-126">Class</span></span>|<span data-ttu-id="79831-127">Необходимое значение для доступа</span><span class="sxs-lookup"><span data-stu-id="79831-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
> <span data-ttu-id="79831-128">Конкретные разрешения не запрашиваются до тех пор, пока не будет вызван метод <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="79831-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="79831-129">Разрешение на вывод файлового диалогового окна не дает приложению полный доступ ко всем членам классов <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="79831-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="79831-130">Точные разрешения, необходимые для вызова каждого метода, см. в справочном разделе по этому методу в документации по библиотеке классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79831-130">For the exact permissions that are required to call each method, see the reference topic for that method in the .NET Framework class library documentation.</span></span>  
  
 <span data-ttu-id="79831-131">В примере кода ниже метод <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> используется для открытия указанного пользователем файла в элементе управления <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="79831-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="79831-132">Для этого требуется разрешение <xref:System.Security.Permissions.FileDialogPermission> и связанное с ним значение перечисления <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="79831-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="79831-133">В примере показано, как обрабатывать исключение <xref:System.Security.SecurityException> для определения того, нужно ли отключить возможность сохранения.</span><span class="sxs-lookup"><span data-stu-id="79831-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="79831-134">В этом примере требуется, чтобы форма <xref:System.Windows.Forms.Form> содержала элемент управления <xref:System.Windows.Forms.Button> с именем `ButtonOpen` и элемент управления <xref:System.Windows.Forms.RichTextBox> с именем `RtfBoxMain`.</span><span class="sxs-lookup"><span data-stu-id="79831-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79831-135">Программная логика для возможности сохранения в примере не представлена.</span><span class="sxs-lookup"><span data-stu-id="79831-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click   
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try   
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()   
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try   
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then   
                ' The application does not have unrestricted permission   
                ' to the file so the save feature will be disabled.  
                saveAllowed = False   
            Else   
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)   
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)   
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())   
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try   
        {  
            editingFileName = openFileDialog1.FileName;  
        }   
        catch (Exception ex)   
        {  
            if (ex is System.Security.SecurityException)   
            {  
                // The application does not have unrestricted permission   
                // to the file so the save feature will be disabled.  
                saveAllowed = false;   
            }   
            else   
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="79831-136">В визуальном C#элементе убедитесь, что добавлен код для включения обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="79831-136">In Visual C#, ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="79831-137">Следующий код показывает, как с помощью кода из предыдущего примера включить обработчик событий: `this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span><span class="sxs-lookup"><span data-stu-id="79831-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="79831-138">Другие файлы</span><span class="sxs-lookup"><span data-stu-id="79831-138">Other Files</span></span>  
 <span data-ttu-id="79831-139">Иногда необходимо считывать или записывать файлы, которые не указываются пользователем, например если требуется сохранить параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="79831-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="79831-140">В зонах локальной интрасети и Интернета приложение не имеет разрешения сохранять данные в локальном файле.</span><span class="sxs-lookup"><span data-stu-id="79831-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="79831-141">Тем не менее приложение может сохранять данные в изолированном хранилище.</span><span class="sxs-lookup"><span data-stu-id="79831-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="79831-142">Изолированное хранилище — это абстрактная секция данных (а не конкретное хранилище), содержащая один или несколько изолированных файлов хранения, называемых хранилищами, которые содержат сведения о действительных папках размещения данных.</span><span class="sxs-lookup"><span data-stu-id="79831-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="79831-143">Разрешения на доступ к файлам, такие как <xref:System.Security.Permissions.FileIOPermission>, не обязательны; вместо этого класс <xref:System.Security.Permissions.IsolatedStoragePermission> управляет разрешениями для изолированного хранилища.</span><span class="sxs-lookup"><span data-stu-id="79831-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="79831-144">По умолчанию приложения, запущенные в зонах локальной интрасети и Интернета, могут хранить данные с помощью изолированного хранилища. Однако такие параметры, как дисковая квота, могут меняться.</span><span class="sxs-lookup"><span data-stu-id="79831-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="79831-145">Дополнительные сведения о изолированном хранении см. в разделе [изолированное хранилище](../../standard/io/isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="79831-145">For more information about isolated storage, see [Isolated Storage](../../standard/io/isolated-storage.md).</span></span>  
  
 <span data-ttu-id="79831-146">В примере ниже для записи данных в файл, расположенный в хранилище, используется изолированное хранилище.</span><span class="sxs-lookup"><span data-stu-id="79831-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="79831-147">Для этого примера требуется разрешение <xref:System.Security.Permissions.IsolatedStorageFilePermission> и значение перечисления <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>.</span><span class="sxs-lookup"><span data-stu-id="79831-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="79831-148">В примере демонстрируется чтение и запись определенных значений свойств элемента управления <xref:System.Windows.Forms.Button> в файл в изолированном хранилище.</span><span class="sxs-lookup"><span data-stu-id="79831-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="79831-149">Функция `Read` может быть вызвана после запуска приложения, а функция `Write` — до окончания работы приложения.</span><span class="sxs-lookup"><span data-stu-id="79831-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="79831-150">В этом примере предполагается, что функции `Read` и `Write` существуют как члены <xref:System.Windows.Forms.Form>, которые содержат элемент управления <xref:System.Windows.Forms.Button> с именем `MainButton`.</span><span class="sxs-lookup"><span data-stu-id="79831-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values   
' for the button if the options file does not exist.  
Public Sub Read()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try   
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _   
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try   
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try   
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _   
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _   
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values   
// for the button if the options file does not exist.  
public void Read()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =   
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try   
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =   
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {   
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }   
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try   
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try   
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new   
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,   
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {   
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="79831-151">Доступ к базе данных</span><span class="sxs-lookup"><span data-stu-id="79831-151">Database Access</span></span>  
 <span data-ttu-id="79831-152">Разрешения, необходимые для доступа к базе данных, различаются в зависимости от поставщика базы данных. Однако только приложения с соответствующими разрешениями могут получить доступ к базе данных через подключение данных.</span><span class="sxs-lookup"><span data-stu-id="79831-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="79831-153">Дополнительные сведения о разрешениях, необходимых для доступа к базе данных, см. в разделе [Безопасность доступа к коду и ADO.NET](../data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="79831-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](../data/adonet/code-access-security.md).</span></span>  
  
 <span data-ttu-id="79831-154">Если невозможно получить доступ к базе данных напрямую, так как требуется, чтобы приложение работало в среде с частичным доверием, можно использовать веб-службу как альтернативное средство доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="79831-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="79831-155">Веб-служба — это программа, доступ к которой можно получить программными средствами по сети.</span><span class="sxs-lookup"><span data-stu-id="79831-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="79831-156">С помощью веб-служб приложения могут совместно использовать данные из различных зон групп кода.</span><span class="sxs-lookup"><span data-stu-id="79831-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="79831-157">По умолчанию приложения в зонах локальной интрасети и Интернета получают право на доступ к исходным сайтам, что позволяет им вызывать веб-службы, размещенные на том же сервере.</span><span class="sxs-lookup"><span data-stu-id="79831-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="79831-158">Дополнительные сведения см. [в статье веб-службы в ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) или [Windows Communication Foundation](../wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="79831-158">For more information see [Web Services in ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) or [Windows Communication Foundation](../wcf/index.md).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="79831-159">Доступ к реестру</span><span class="sxs-lookup"><span data-stu-id="79831-159">Registry Access</span></span>  
 <span data-ttu-id="79831-160">Класс <xref:System.Security.Permissions.RegistryPermission> управляет доступом к реестру операционной системы.</span><span class="sxs-lookup"><span data-stu-id="79831-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="79831-161">По умолчанию доступ к реестру могут получить только приложения, которые работают локально.</span><span class="sxs-lookup"><span data-stu-id="79831-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="79831-162">Разрешение <xref:System.Security.Permissions.RegistryPermission> предоставляет приложению право всего лишь попытаться получить доступ к реестру, но не гарантирует, что доступ будет успешно получен, потому что операционная система принудительно обеспечивает безопасность реестра.</span><span class="sxs-lookup"><span data-stu-id="79831-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="79831-163">Так как в среде с частичным доверием доступ к реестру получить невозможно, могут потребоваться другие способы хранения данных.</span><span class="sxs-lookup"><span data-stu-id="79831-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="79831-164">Для хранения параметров приложения используйте вместо реестра изолированное хранилище.</span><span class="sxs-lookup"><span data-stu-id="79831-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="79831-165">Изолированное сохранение можно использовать также для хранения файлов, относящихся к приложению.</span><span class="sxs-lookup"><span data-stu-id="79831-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="79831-166">Можно хранить общие сведения приложения о сервере или исходном сайте, так как по умолчанию приложение имеет право на доступ к исходному сайту.</span><span class="sxs-lookup"><span data-stu-id="79831-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79831-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="79831-167">See also</span></span>

- [<span data-ttu-id="79831-168">Более безопасная печать в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79831-168">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)
- [<span data-ttu-id="79831-169">Дополнительные вопросы безопасности в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79831-169">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="79831-170">Общие сведения о безопасности в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79831-170">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="79831-171">Безопасность Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79831-171">Windows Forms Security</span></span>](windows-forms-security.md)
- [<span data-ttu-id="79831-172">Mage.exe (средство создания и редактирования манифеста)</span><span class="sxs-lookup"><span data-stu-id="79831-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../tools/mage-exe-manifest-generation-and-editing-tool.md)
- [<span data-ttu-id="79831-173">MageUI.exe (средство создания и редактирования манифестов, графический клиент)</span><span class="sxs-lookup"><span data-stu-id="79831-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)

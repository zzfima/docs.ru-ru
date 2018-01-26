---
title: "Практическое руководство. Открытие файлов с помощью компонента OpenFileDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fabe176ade1ae94a20100162ab7ab6fadfb2999f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a>Практическое руководство. Открытие файлов с помощью компонента OpenFileDialog
<xref:System.Windows.Forms.OpenFileDialog> Компонент позволяет пользователям просматривать папки на компьютере или на любом компьютере в сети и выбрать один или несколько файлов для открытия. Диалоговое окно возвращает путь и имя файла, который пользователь выбрал в диалоговом окне.  
  
 После выбора открываемого файла существует два подхода к открытию файла. Если вы предпочитаете работать с потоками файлов, можно создать экземпляр <xref:System.IO.StreamReader> класса. Кроме того, можно использовать <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод, чтобы открыть выбранный файл.  
  
 В первом примере включает в себя <xref:System.Security.Permissions.FileIOPermission> проверка разрешений (как описано в «Примечание по безопасности» ниже), но также предоставляет доступ к имени файла. Этот метод можно использовать из зоны локального компьютера, интрасети и Интернета. Второй метод также выполняет <xref:System.Security.Permissions.FileIOPermission> проверку разрешений, но лучше всего подходит для приложений в зоне интрасети или Интернету.  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a>Открытие файла как потока с помощью компонента OpenFileDialog  
  
1.  Выведите на экран диалоговое окно **Открыть файл** и вызовите метод для открытия файла, выбранного пользователем.  
  
     Один подход заключается в использовании <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы открыть диалоговое окно открытия файла и использовать экземпляр <xref:System.IO.StreamReader> класс, чтобы открыть файл.  
  
     В приведенном ниже используется <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий, чтобы открыть экземпляр <xref:System.Windows.Forms.OpenFileDialog> компонента. Если файл выбран и пользователь нажимает кнопку **ОК**, открывается файл, выбранный в диалоговом окне. В этом случае содержимое отображается в окне сообщения, чтобы показать, что файловый поток считан.  
  
    > [!IMPORTANT]
    >  Чтобы получить или задать <xref:System.Windows.Forms.FileDialog.FileName%2A> свойства, сборка требует уровня прав доступа предоставляемых по <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> класса. Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     В этом примере предполагается, имеет форму <xref:System.Windows.Forms.Button> управления и <xref:System.Windows.Forms.OpenFileDialog> компонента.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Дополнительные сведения о чтении из файлового потока см. в разделе <xref:System.IO.FileStream.BeginRead%2A> и <xref:System.IO.FileStream.Read%2A>.  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a>Открытие файла как файла с помощью компонента OpenFileDialog  
  
1.  Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы отобразить диалоговое окно и <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод для открытия файла.  
  
     <xref:System.Windows.Forms.OpenFileDialog> Компонента <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод возвращает количество байтов, составляющих файл. Эти байты образуют поток для считывания. В следующем примере <xref:System.Windows.Forms.OpenFileDialog> экземпляр компонента с фильтром по «курсор»`.cur`. Если выбран файл `.cur`, в качестве курсора формы задается выбранный курсор.  
  
    > [!IMPORTANT]
    >  Для вызова <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод, сборка требует уровня прав доступа предоставляемых по <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> класса. Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     В этом примере предполагается, имеет форму <xref:System.Windows.Forms.Button> элемента управления.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [Компонент OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)

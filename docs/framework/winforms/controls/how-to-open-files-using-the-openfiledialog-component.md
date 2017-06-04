---
title: "Практическое руководство. Открытие файлов с помощью компонента OpenFileDialog | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "файлы, открытие с помощью компонента OpenFileDialog"
  - "OpenFile - метод"
  - "OpenFile - метод, OpenFileDialog - компонент"
  - "OpenFileDialog - компонент, открытие файлов"
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Открытие файлов с помощью компонента OpenFileDialog
Компонент <xref:System.Windows.Forms.OpenFileDialog> позволяет пользователям просматривать папки личного компьютера или любого компьютера в сети, а также выбирать файлы, которые требуется открыть.  Диалоговое окно возвращает путь и имя файла, который был выбран пользователем.  
  
 После того, как пользователь выбирает файл, который требуется открыть, существует два подхода к открытию файла.  Если разработчик предпочитает работать с потоками файлов, можно создать экземпляр класса <xref:System.IO.StreamReader>.  С другой стороны, для открытия выбранного файла можно использовать метод <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>.  
  
 В первом примере, представленном ниже, используется проверка разрешения <xref:System.Security.Permissions.FileIOPermission> \(согласно описанию в примечании о безопасности ниже\), но обеспечивается доступ к имени файла.  Можно использовать этот способ в зонах "Локальный компьютер", "Интрасеть" и "Интернет".  Во втором методе также проводится проверка разрешения <xref:System.Security.Permissions.FileIOPermission>, однако этот метод больше подходит для приложений в зонах "Интрасеть" или "Интернет".  
  
### Чтобы открыть файл в виде потока с помощью компонента OpenFileDialog  
  
1.  Отобразите диалоговое окно **Открытие файла** и вызовите метод, чтобы открыть файл, выбранный пользователем.  
  
     Можно использовать метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна "Открытие файла", а экземпляр класса <xref:System.IO.StreamReader> использовать для открытия файла.  
  
     В приведенном ниже используется обработчик событий <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> для открытия экземпляра компонента <xref:System.Windows.Forms.OpenFileDialog>.  Когда файл выбран и пользователь нажимает кнопку **ОК**, файл, выбранный в диалоговом окне, открывается.  В этом случае отображается содержимое окна сообщения, чтобы показать, что поток файла прочитан.  
  
    > [!IMPORTANT]
    >  Чтобы получить или задать свойство <xref:System.Windows.Forms.FileDialog.FileName%2A>, сборка требует уровня привилегий, предоставляемых классом <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>.  Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из\-за недостатка привилегий.  Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     Пример предполагает, что в форме есть элемент управления <xref:System.Windows.Forms.Button> и компонент <xref:System.Windows.Forms.OpenFileDialog>.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Дополнительные сведения о чтении из файловых потоков можно найти в разделах [Метод FileStream.BeginRead Method](frlrfSystemIOFileStreamClassBeginReadTopic) и [Метод FileStream.Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx).  
  
### Чтобы открыть файл в виде файла с помощью компонента OpenFileDialog  
  
1.  Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна  и метода <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> для открытия файла.  
  
     Метод <xref:System.Windows.Forms.OpenFileDialog> компонента <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> возвращает байты, по которым собирается файл.  Эти байты образуют поток для считывания.  В примере, представленном ниже, создается экземпляр компонента <xref:System.Windows.Forms.OpenFileDialog> с фильтром по "курсору". Таким образом, пользователь сможет выбирать только файлы с расширением `.cur` Если выбрать файл `.cur` , курсор формы помещается на выбранный курсор.  
  
    > [!IMPORTANT]
    >  Чтобы вызвать метод <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>, сборка требует уровня прав доступа, предоставляемых классом <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>.  Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из\-за недостатка привилегий.  Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     В примере предполагается, что в форме существует элемент управления <xref:System.Windows.Forms.Button>.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [Компонент OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
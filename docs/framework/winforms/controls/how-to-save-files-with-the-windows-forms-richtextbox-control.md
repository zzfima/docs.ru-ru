---
title: "Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms | Microsoft Docs"
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
  - "RTF-файлы, сохранение в элементе управления RichTextBox"
  - "примеры [Windows Forms], текстовые поля"
  - "файлы, сохранение с помощью элемента управления RichTextBox"
  - "RichTextBox - элемент управления [Windows Forms], сохранение файлов"
  - "RTF-файлы, сохранение в элементе управления RichTextBox"
  - "сохранение файлов"
  - "сохранение файлов, RichTextBox - элемент управления"
  - "текстовые файлы, сохранение из элемента управления RichTextBox"
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> позволяет записывать отображаемые в нем данные в одном из следующих форматов:  
  
-   Обычный текст  
  
-   Текст в Юникоде  
  
-   Формат RTF \(Rich Text Format\)  
  
-   Формат RTF с пропусками на месте объектов OLE  
  
-   Обычный текст с текстовым представлением объектов OLE  
  
 Чтобы сохранить файл, вызовите метод <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>.  Метод **SaveFile** также можно использовать для записи данных в поток.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### Сохранение содержимого элемента управления в файле  
  
1.  Определите путь к файлу, в который будет производиться запись.  
  
     На практике для этого обычно используется компонент <xref:System.Windows.Forms.SaveFileDialog>.  Для получения общих сведений см. [Общие сведения о компоненте SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).  
  
2.  Вызовите метод <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> элемента управления <xref:System.Windows.Forms.RichTextBox>, указав имя файла для сохранения и, если необходимо, его тип.  Если метод вызван только с одним аргументом — именем файла, то файл будет сохранен в формате RTF.  Чтобы определить другой тип файла, вызовите метод, использовав в качестве второго аргумента одно из значений перечисления <xref:System.Windows.Forms.RichTextBoxStreamType>.  
  
     В приведенном ниже примере в качестве местоположения RTF\-файла выбрана папка **Мои документы**.  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  В примере, представленном ниже, подразумевается, что элемент управления <xref:System.Windows.Forms.RichTextBox> уже добавлен в форму.  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Если такого файла не существует, этот пример создает новый файл.  Чтобы приложение могло создать файл, ему необходимо иметь доступ к папке с правом на создание файлов.  Для задания разрешений используется список управления доступом.  Если файл уже существует, то приложению достаточно иметь лишь доступ с правом на запись, т. е. с меньшими привилегиями.  По соображениям безопасности целесообразнее создать файл во время развертывания, если это возможно, и предоставить право на чтение отдельного файла, а не право на создание файлов в папке.  По тем же соображениям рекомендуется сохранять данные в пользовательских каталогах, а не в корневом каталоге или каталоге Program Files.  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
---
title: "How to: Add Data to the Clipboard | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Clipboard, copying data to"
  - "data [Windows Forms], copying to Clipboard"
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Add Data to the Clipboard
Класс <xref:System.Windows.Forms.Clipboard> предоставляет методы, которые можно использовать для взаимодействия с функцией буфера обмена операционной системы Windows.  Многие приложения используют буфер обмена в качестве временного хранилища данных.  Например, текстовые процессоры используют буфер обмена во время операций вырезания и вставки.  Буфер обмена также полезен для передачи данных из одного приложения в другое.  
  
 При добавлении данных в буфер обмена можно указать формат данных таким образом, чтобы другие приложения могли распознать данные, если они могут использовать этот формат.  Можно также добавить данные в буфер обмена в нескольких различных форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные.  
  
 Формат буфера обмена является строкой, которая определяет формат таким образом, чтобы приложение, использующее этот формат, могло получать связанные данные.  Класс <xref:System.Windows.Forms.DataFormats> предоставляет предварительно определенные имена форматов для использования.  Можно также использовать собственные имена форматов или использовать тип объекта в качестве его формата.  
  
 Чтобы добавить данные в буфер обмена в одном или нескольких форматах, используйте метод <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.  Этому методу можно передать любой объект, но для добавления данных в нескольких форматах необходимо сначала добавить данные в отдельный объект, предназначенный для работы с несколькими форматами данных.  Обычно данные добавляются к объекту <xref:System.Windows.Forms.DataObject>, но можно использовать любой тип, реализующий интерфейс <xref:System.Windows.Forms.IDataObject>.  
  
 В [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] можно добавить данные непосредственно в буфер обмена с помощью новых методов, позволяющих упростить основные задачи при работе с буфером обмена.  Используйте эти методы при работе с данными в одном общем формате, такими как текст.  
  
> [!NOTE]
>  Все приложения Windows используют один буфер обмена.  Поэтому содержимое буфера обмена может изменяться при переходе к другому приложению.  
>   
>  Класс <xref:System.Windows.Forms.Clipboard> может использоваться только в потоках в режиме однопотокового подразделения.  Чтобы использовать этот класс, убедитесь, что используемый метод `Main` помечен атрибутом <xref:System.STAThreadAttribute>.  
>   
>  Для помещения в буфер обмена объект должен быть сериализуемым.  Чтобы сделать тип сериализуемым, его необходимо пометить атрибутом <xref:System.SerializableAttribute>.  Если методу буфера обмена передается не сериализуемый объект, метод завершится неудачей без создания исключения.  Дополнительные сведений о сериализации см. в разделе <xref:System.Runtime.Serialization>.  
  
### Чтобы добавить данные в буфер обмена в одном общем формате, выполните следующие действия.  
  
1.  Используйте метод <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A> или <xref:System.Windows.Forms.Clipboard.SetText%2A>.  Эти методы доступны только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### Чтобы добавить данные в буфер обмена в пользовательском формате, выполните следующие действия.  
  
1.  Используйте метод <xref:System.Windows.Forms.Clipboard.SetData%2A> с именем пользовательского формата.  Этот метод доступен только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Можно также использовать предварительно определенные имена форматов с помощью метода <xref:System.Windows.Forms.Clipboard.SetData%2A>.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### Чтобы добавить данные в буфер обмена в нескольких форматах, выполните следующие действия.  
  
1.  Используйте метод <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> и передайте ему объект <xref:System.Windows.Forms.DataObject>, содержащий данные.  Необходимо использовать этот метод для добавления данных в буфер обмена для более ранних версий, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## См. также  
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
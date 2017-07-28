---
title: "How to: Retrieve Data from the Clipboard | Microsoft Docs"
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
  - "pasting Clipboard data"
  - "Clipboard, retrieving data"
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Retrieve Data from the Clipboard
Класс <xref:System.Windows.Forms.Clipboard> предоставляет методы, которые можно использовать для взаимодействия с функцией буфера обмена операционной системы Windows.  Многие приложения используют буфер обмена в качестве временного хранилища данных.  Например, текстовые процессоры используют буфер обмена во время операций вырезания и вставки.  Буфер обмена также полезен для передачи данных из одного приложения в другое.  
  
 Некоторые приложения хранят данные в буфере обмена в нескольких форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные.  Формат буфера обмена является строкой, которая определяет формат.  Приложение, использующее указанный формат, может извлечь связанные данные из буфера обмена.  Класс <xref:System.Windows.Forms.DataFormats> предоставляет предварительно определенные имена форматов для использования.  Можно также использовать собственные имена форматов или использовать тип объекта в качестве его формата.  Сведения о добавлении данных в буфер обмена см. в разделе [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).  
  
 Чтобы определить, содержит ли буфер обмена данные в определенном формате, используйте один из методов `Contains`*Формат* или метод <xref:System.Windows.Forms.Clipboard.GetData%2A>.  Чтобы извлечь данные из буфера обмена, воспользуйтесь одним из методов `Get`*Формат* или методом <xref:System.Windows.Forms.Clipboard.GetData%2A>.  Эти методы являются новыми в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Для доступа к данным из буфера обмена с помощью более ранних версий, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], используйте метод <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> и вызывайте методы возвращаемого интерфейса <xref:System.Windows.Forms.IDataObject>.  Чтобы определить, является ли доступным определенный формат в возвращаемом объекте, вызовите, например, метод <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>.  
  
> [!NOTE]
>  Все приложения Windows используют один системный буфер обмена.  Поэтому содержимое буфера обмена может изменяться при переходе к другому приложению.  
>   
>  Класс <xref:System.Windows.Forms.Clipboard> может использоваться только в потоках в режиме однопотокового подразделения.  Чтобы использовать этот класс, убедитесь, что используемый метод `Main` помечен атрибутом <xref:System.STAThreadAttribute>.  
  
### Для получения данных из буфера обмена в одном стандартном формате, выполните следующие действия.  
  
1.  Используйте метод <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A> или <xref:System.Windows.Forms.Clipboard.GetText%2A>.  При необходимости используйте сначала соответствующие методы `Contains`*Формат*, чтобы определить, доступны ли данные в определенном формате.  Эти методы доступны только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### Для извлечения данных из буфера обмена в пользовательском формате, выполните следующие действия.  
  
1.  Используйте метод <xref:System.Windows.Forms.Clipboard.GetData%2A> с именем пользовательского формата.  Этот метод доступен только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Можно также использовать предварительно определенные имена форматов с помощью метода <xref:System.Windows.Forms.Clipboard.SetData%2A>.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### Для извлечения данных из буфера обмена в нескольких форматах, выполните следующие действия.  
  
1.  Используйте метод <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>.  Этот метод необходимо использовать для извлечения данных из буфера обмена для более ранних версий, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## См. также  
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)   
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
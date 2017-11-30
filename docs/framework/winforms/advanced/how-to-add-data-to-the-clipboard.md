---
title: "Практическое руководство. Добавление данных в буфер обмена"
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
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47858af6d4e3dc5f29632c5a74f2431a2cc200b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a>Практическое руководство. Добавление данных в буфер обмена
<xref:System.Windows.Forms.Clipboard> Класс предоставляет методы, которые можно использовать для взаимодействия с компонентом буфер обмена операционной системы Windows. Многие приложения используют буфер обмена в качестве временного хранилища данных. Например текстовые редакторы использовать буфер обмена во время операций вырезания и вставки. Буфер обмена также полезен для передачи данных из одного приложения в другое.  
  
 При добавлении данных в буфер обмена, чтобы другие приложения могли распознать данные, если они могут использовать этот формат можно указать формат данных. Можно также добавлять данные в буфер обмена в нескольких различных форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные.  
  
 Формат буфера обмена является строка, определяющая формат, чтобы приложение, использующее этот формат может получать связанные данные. <xref:System.Windows.Forms.DataFormats> Класс предоставляет имена стандартных форматов для использования. Можно также использовать собственные имена форматов или использовать тип объекта в качестве его формата.  
  
 Чтобы добавить данные в буфер обмена в один или несколько форматов, используйте <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> метод. Этот метод можно передать любой объект, но для добавления данных в нескольких форматах, необходимо добавить данные отдельный объект, предназначенный для работы с несколькими форматами. Как правило, вы добавите данные не будут <xref:System.Windows.Forms.DataObject>, но можно использовать любой тип, реализующий <xref:System.Windows.Forms.IDataObject> интерфейса.  
  
 В [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], можно добавить данные непосредственно в буфер обмена с помощью новых методов, позволяющих упростить основные задачи в буфер обмена. Эти методы можно используйте при работе с данными в одном общем формате такие как текст.  
  
> [!NOTE]
>  Все приложения Windows используют один буфер обмена. Таким образом содержимое могут быть изменены при переходе в другое приложение.  
>   
>  <xref:System.Windows.Forms.Clipboard> Класс может использоваться только в потоках в режим однопотоковое подразделение (STA). Чтобы использовать этот класс, убедитесь, что ваш `Main` метод помечен атрибутом <xref:System.STAThreadAttribute> атрибута.  
>   
>  Объект должен поддерживать сериализацию для помещения в буфер обмена. Чтобы сделать тип сериализуемым, его необходимо пометить <xref:System.SerializableAttribute> атрибута. Если методу буфера обмена передается несериализуемый объект, метод завершится с ошибкой без вызова исключения. Дополнительные сведения о сериализации см. в разделе <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Чтобы добавить данные в буфер обмена в одном общем формате  
  
1.  Используйте <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, или <xref:System.Windows.Forms.Clipboard.SetText%2A> метод. Эти методы доступны только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Чтобы добавить данные в буфер обмена в пользовательском формате  
  
1.  Используйте <xref:System.Windows.Forms.Clipboard.SetData%2A> метод с именем пользовательского формата. Этот метод доступен только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Можно также использовать имена стандартных форматов с <xref:System.Windows.Forms.Clipboard.SetData%2A> метод. Для получения дополнительной информации см. <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Чтобы добавить данные в буфер обмена в нескольких форматах  
  
1.  Используйте <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> метод и передайте его в <xref:System.Windows.Forms.DataObject> , содержащий нужные данные. Необходимо использовать этот метод для добавления данных в буфер обмена для версий более ранних, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>См. также  
 [Операции перетаскивания и поддержка буфера обмена](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [Практическое руководство. Извлечение данных из буфера обмена](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)

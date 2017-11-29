---
title: "Практическое руководство. Извлечение данных из буфера обмена"
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
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2f71c6738f19e70826b95626377097de0cd9b3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Практическое руководство. Извлечение данных из буфера обмена
<xref:System.Windows.Forms.Clipboard> Класс предоставляет методы, которые можно использовать для взаимодействия с компонентом буфер обмена операционной системы Windows. Многие приложения используют буфер обмена в качестве временного хранилища данных. Например текстовые редакторы использовать буфер обмена во время операций вырезания и вставки. Буфер обмена также полезен для передачи данных из одного приложения в другое.  
  
 Некоторые приложения сохраняют данные в буфер обмена в нескольких форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные. Формат буфера обмена является строкой, которая определяет формат. Приложение, использующее указанный формат можно получить связанные данные в буфер обмена. <xref:System.Windows.Forms.DataFormats> Класс предоставляет имена стандартных форматов для использования. Можно также использовать собственные имена форматов или использовать тип объекта в качестве его формата. Сведения о добавлении данных в буфер обмена см. в разделе [как: добавить данные в буфер обмена](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).  
  
 Чтобы определить, содержит ли буфер данных в определенном формате, используйте один из `Contains` *формат* методы или <xref:System.Windows.Forms.Clipboard.GetData%2A> метод. Для получения данных из буфера обмена, используйте один из `Get` *формат* методы или <xref:System.Windows.Forms.Clipboard.GetData%2A> метод. Эти методы являются новыми в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Для доступа к данным из буфера обмена с помощью версии более ранней, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], используйте <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> метод и вызывать методы возвращаемого <xref:System.Windows.Forms.IDataObject>. Чтобы определить, доступен ли определенный формат в возвращаемом объекте, например, вызов <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> метод.  
  
> [!NOTE]
>  Все приложения, на основе Windows используют буфер обмена системы. Таким образом содержимое могут быть изменены при переходе в другое приложение.  
>   
>  <xref:System.Windows.Forms.Clipboard> Класс может использоваться только в потоках в режим однопотоковое подразделение (STA). Чтобы использовать этот класс, убедитесь, что ваш `Main` метод помечен атрибутом <xref:System.STAThreadAttribute> атрибута.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Для получения данных из буфера обмена в одном общем формате  
  
1.  Используйте <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, или <xref:System.Windows.Forms.Clipboard.GetText%2A> метод. При необходимости используйте соответствующий `Contains` *формат* методы, чтобы определить, доступен ли данные в определенном формате. Эти методы доступны только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Для получения данных из буфера обмена в пользовательском формате  
  
1.  Используйте <xref:System.Windows.Forms.Clipboard.GetData%2A> метод с именем пользовательского формата. Этот метод доступен только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Можно также использовать имена стандартных форматов с <xref:System.Windows.Forms.Clipboard.SetData%2A> метод. Для получения дополнительной информации см. <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Для получения данных из буфера обмена в нескольких форматах  
  
1.  Воспользуйтесь методом <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. Необходимо использовать этот метод для извлечения данных из буфера обмена для версий более ранних, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>См. также  
 [Операции перетаскивания и поддержка буфера обмена](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [Практическое руководство. Добавление данных в буфер обмена](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)

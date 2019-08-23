---
title: Практическое руководство. Добавление данных в буфер обмена
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: d4afcd6ce942d1cd2286e3f393ce61436821bb3a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955130"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Практическое руководство. Добавление данных в буфер обмена
<xref:System.Windows.Forms.Clipboard> Класс предоставляет методы, которые можно использовать для взаимодействия с функцией буфера обмена операционной системы Windows. Многие приложения используют буфер обмена в качестве временного репозитория для данных. Например, текстовые редакторы используют буфер обмена во время операций вырезания и вставки. Буфер обмена также полезен для передачи данных из одного приложения в другое.  
  
 При добавлении данных в буфер обмена можно указать формат данных, чтобы другие приложения могли распознать данные, если они могут использовать этот формат. Можно также добавить данные в буфер обмена в различных форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные.  
  
 Формат буфера обмена — это строка, которая определяет формат, чтобы приложение, использующее этот формат, могла извлекать связанные данные. <xref:System.Windows.Forms.DataFormats> Класс предоставляет стандартные имена форматов для использования. Можно также использовать собственные имена форматов или использовать тип объекта в качестве его формата.  
  
 Чтобы добавить данные в буфер обмена в одном или нескольких форматах, используйте <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> метод. В этот метод можно передать любой объект, но для добавления данных в нескольких форматах необходимо сначала добавить данные в отдельный объект, предназначенный для работы с несколькими форматами. Как правило, данные добавляются в <xref:System.Windows.Forms.DataObject>, но можно использовать любой тип, <xref:System.Windows.Forms.IDataObject> реализующий интерфейс.  
  
 В .NET Framework 2,0 можно добавлять данные непосредственно в буфер обмена, используя новые методы, предназначенные для упрощения выполнения основных задач в буфере обмена. Используйте эти методы при работе с данными в одном общем формате, например в тексте.  
  
> [!NOTE]
> Все приложения на базе Windows используют буфер обмена. Поэтому содержимое может измениться при переключении на другое приложение.  
>   
>  <xref:System.Windows.Forms.Clipboard> Класс может использоваться только в потоках, для которых установлен режим апартамента однопотокового подразделения (STA). Чтобы использовать этот класс, убедитесь, что `Main` ваш метод помечен <xref:System.STAThreadAttribute> атрибутом.  
>   
>  Объект должен быть сериализуемым, чтобы его можно было разместить в буфере обмена. Чтобы сделать тип сериализуемым, пометьте его <xref:System.SerializableAttribute> атрибутом. Если передать несериализуемый объект в метод буфера обмена, метод завершится с ошибкой, не вызывая исключение. Дополнительные сведения о сериализации см. в разделе <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Добавление данных в буфер обмена в одном общем формате  
  
1. Используйте метод <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A> ,,<xref:System.Windows.Forms.Clipboard.SetImage%2A>или .<xref:System.Windows.Forms.Clipboard.SetText%2A> <xref:System.Windows.Forms.Clipboard.SetAudio%2A> Эти методы доступны только в .NET Framework 2,0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Добавление данных в буфер обмена в пользовательском формате  
  
1. <xref:System.Windows.Forms.Clipboard.SetData%2A> Используйте метод с именем пользовательского формата. Этот метод доступен только в .NET Framework 2,0.  
  
     Можно также использовать предопределенные имена форматов с <xref:System.Windows.Forms.Clipboard.SetData%2A> помощью метода. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Добавление данных в буфер обмена в нескольких форматах  
  
1. Используйте метод и передайте объект <xref:System.Windows.Forms.DataObject> , который содержит ваши данные. <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> Этот метод необходимо использовать для добавления данных в буфер обмена в версиях, предшествующих .NET Framework 2,0.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>См. также

- [Операции перетаскивания и поддержка буфера обмена](drag-and-drop-operations-and-clipboard-support.md)
- [Практическое руководство. Получение данных из буфера обмена](how-to-retrieve-data-from-the-clipboard.md)

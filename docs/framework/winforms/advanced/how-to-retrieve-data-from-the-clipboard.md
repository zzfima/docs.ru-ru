---
title: Практическое руководство. Извлечение данных из буфера обмена
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: ca24615049abcc145698c033f31e6c98a38253bf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040569"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Практическое руководство. Извлечение данных из буфера обмена

<xref:System.Windows.Forms.Clipboard> Класс предоставляет методы, которые можно использовать для взаимодействия с функцией буфера обмена операционной системы Windows. Многие приложения используют буфер обмена в качестве временного репозитория для данных. Например, текстовые редакторы используют буфер обмена во время операций вырезания и вставки. Буфер обмена также полезен для передачи информации из одного приложения в другое.

Некоторые приложения хранят данные в буфере обмена в нескольких форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные. Формат буфера обмена — это строка, идентифицирующая формат. Приложение, использующее идентифицированный формат, может извлекать связанные данные из буфера обмена. <xref:System.Windows.Forms.DataFormats> Класс предоставляет стандартные имена форматов для использования. Можно также использовать собственные имена форматов или использовать тип объекта в качестве своего формата. Сведения о добавлении данных в буфер обмена см. в [разделе как Добавление данных в буфер обмена](how-to-add-data-to-the-clipboard.md).

Чтобы определить, содержит ли буфер обмена данные в определенном формате, используйте один из `Contains`методов *Format* или <xref:System.Windows.Forms.Clipboard.GetData%2A> метод. Чтобы получить данные из буфера обмена, используйте один из `Get`методов *Format* или <xref:System.Windows.Forms.Clipboard.GetData%2A> метод. Эти методы являются новыми в .NET Framework 2,0.

Чтобы получить доступ к данным из буфера обмена с использованием более ранних версий, чем <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> .NET Framework 2,0, используйте метод и вызовите <xref:System.Windows.Forms.IDataObject>методы возвращаемого объекта. Чтобы определить, доступен ли определенный формат в возвращаемом объекте, например, вызовите <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> метод.

> [!NOTE]
> Все приложения на базе Windows совместно используют буфер обмена системы. Поэтому содержимое может измениться при переключении на другое приложение.
>
> <xref:System.Windows.Forms.Clipboard> Класс может использоваться только в потоках, для которых установлен режим апартамента однопотокового подразделения (STA). Чтобы использовать этот класс, убедитесь, что `Main` ваш метод помечен <xref:System.STAThreadAttribute> атрибутом.

### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Получение данных из буфера обмена в одном общем формате

1. Используйте метод <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A> ,,<xref:System.Windows.Forms.Clipboard.GetImage%2A>или .<xref:System.Windows.Forms.Clipboard.GetText%2A> <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A> При необходимости сначала используйте соответствующие `Contains`методы *форматирования* , чтобы определить, доступны ли данные в определенном формате. Эти методы доступны только в .NET Framework 2,0.

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Извлечение данных из буфера обмена в пользовательском формате

1. <xref:System.Windows.Forms.Clipboard.GetData%2A> Используйте метод с именем пользовательского формата. Этот метод доступен только в .NET Framework 2,0.

    Можно также использовать предопределенные имена форматов с <xref:System.Windows.Forms.Clipboard.SetData%2A> помощью метода. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DataFormats>.

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Извлечение данных из буфера обмена в нескольких форматах

1. Воспользуйтесь методом <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. Этот метод необходимо использовать для получения данных из буфера обмена в версиях, предшествующих .NET Framework 2,0.

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>См. также

- [Операции перетаскивания и поддержка буфера обмена](drag-and-drop-operations-and-clipboard-support.md)
- [Практическое руководство. Добавление данных в буфер обмена](how-to-add-data-to-the-clipboard.md)

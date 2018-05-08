---
title: Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: c7c05eb8d858c1f911e148def1c714e3caf74c95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a>Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными
Зачастую при привязке базовых бизнес-объектов к элементам управления возникают ошибки и исключения. Эти ошибки и исключения можно перехватывать, а затем исправлять или передавать сведения об ошибке пользователю путем обработки события <xref:System.Windows.Forms.Binding.BindingComplete> для конкретного компонента <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> или <xref:System.Windows.Forms.CurrencyManager>.  
  
## <a name="example"></a>Пример  
 В данном примере кода показан способ обработки ошибок и исключений, возникающих при выполнении операции привязки данных. Он демонстрирует перехват ошибок путем обработки события <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> объектов <xref:System.Windows.Forms.Binding>. Для перехвата ошибок и исключений с помощью обработки этого события необходимо включить поддержку форматирования для привязки. Форматирование можно включить при создании привязки или добавлении в коллекцию привязок, или установив значение свойства <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> равным `true`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 Во время выполнения, если введена пустая строка в качестве имени или значение меньше 100 в качестве числа, то появится окно с сообщением. Это происходит в результате обработки события <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> для привязок этих текстовых полей.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также построить этот пример, в Visual Studio, вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>  
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)

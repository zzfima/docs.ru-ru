---
title: Практическое руководство. Добавление операторов трассировки в код приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], conditional writes based on switches
- trace statements
- WriteLineIf method
- tracing [.NET Framework], adding trace statements
- Assert method, tracing code
- trace switches, conditional writes based on switches
- WriteIf method
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
ms.openlocfilehash: 9903a0357d1d8ceade21b590fd54c8cab517f134
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174749"
---
# <a name="how-to-add-trace-statements-to-application-code"></a>Практическое руководство. Добавление операторов трассировки в код приложения
Методы, наиболее часто используемые для отслеживания, — это методы для записи выходных данных в прослушиватели: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** и **Fail**. Эти методы можно разделить на две категории: **Write**, **WriteLine** и **Fail** выдают выходные данные безусловно, в то время как методы **WriteIf**, **WriteLineIf** и **Assert** тестируют условие Boolean и выполняют или не выполняют запись в зависимости от значения условия. **WriteIf** и **WriteLineIf** выдают выходные данные, если условие равно `true`, а **Assert** выдает выходные данные, если условие равно `false`.  
  
 При разработке своей стратегии трассировки и отладки следует подумать о способе представления вывода. При наличии нескольких операторов **Write**, заполненных несвязанными данными, получается сложный для чтения журнал. С другой стороны, при использовании метода **WriteLine** для размещения связанных операторов на разных строках может быть сложно понять, какие сведения связаны друг с другом. Как правило, при использовании нескольких операторов **Write** имеет смысл объединить информацию из разных источников для создания единого информационного сообщения и использовать оператор **WriteLine** для создания единого полного сообщения.  
  
### <a name="to-write-a-complete-line"></a>Запись полной строки  
  
1. Вызовите метод <xref:System.Diagnostics.Trace.WriteLine%2A> или <xref:System.Diagnostics.Trace.WriteLineIf%2A>.  
  
     Символ возврата каретки добавляется в конец сообщения, возвращаемого этим методом, чтобы следующее сообщение, возвращаемое методом **Write**, **WriteIf**, **WriteLine** или **WriteLineIf**, начиналось со следующей строки:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,
       "Error in AppendData procedure.");  
    ```  
  
### <a name="to-write-a-partial-line"></a>Запись частичной строки  
  
1. Вызовите метод <xref:System.Diagnostics.Trace.Write%2A> или <xref:System.Diagnostics.Trace.WriteIf%2A>.  
  
     Следующее сообщение, выдаваемое оператором **Write**, **WriteIf**, **WriteLine** или **WriteLineIf**, начинается на той же строке, что и сообщение, выданное оператором **Write** или **WriteIf**:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
    ```  
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a>Проверка наличия определенного условия до или после выполнения метода  
  
1. Вызовите метод <xref:System.Diagnostics.Trace.Assert%2A> .  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > Оператор **Assert** можно использовать и для отладки, и для трассировки. В этом примере стек вызовов выводится в любой прослушиватель в коллекции **Listeners**. Дополнительные сведения см. в разделах [Утверждения в управляемом коде](/visualstudio/debugger/assertions-in-managed-code) и <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [Трассировка и оборудование приложений](tracing-and-instrumenting-applications.md)
- [Практическое руководство. Создание, инициализация и настройка переключателей трассировки](how-to-create-initialize-and-configure-trace-switches.md)
- [Переключатели трассировки](trace-switches.md)
- [Прослушиватели трассировки](trace-listeners.md)

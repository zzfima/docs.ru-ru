---
redirect_url: /dotnet/articles/csharp/programming-guide/interop/
caps.handback.revision: 31
---
# Взаимодействие (Руководство по программированию в C#)
Возможность взаимодействия позволяет использовать существующие вложения в неуправляемый код.  Код, выполняющийся под управлением среды CLR, называется *управляемым кодом*, а код, выполняемый вне этой среды, называется *неуправляемым*.  Примерами неуправляемого программного кода могут служить компоненты COM, COM\+, C\+\+, ActiveX и Microsoft Win32 API.  
  
 Платформа [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] обеспечивает взаимодействие с неуправляемым кодом посредством служб вызова неуправляемого кода, пространства имен <xref:System.Runtime.InteropServices>, взаимодействия C\+\+ и COM\-взаимодействия.  
  
## Содержание  
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 Описываются методы взаимодействия между управляемым кодом C\# и неуправляемым кодом.  
  
 [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 Описывает возможности, представленные в Visual C\# 2010 для облегчения программирования Office.  
  
 [Практическое руководство. Использование индексированных свойств в программировании COM\-взаимодействия](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 Описывает способы использования индексированных свойств для доступа к свойствам COM, которые содержат параметры.  
  
 [Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 Описывает использования служб вызова неуправляемого кода для воспроизведения звукового WAV\-файла в операционной системе Windows.  
  
 [Пошаговое руководство. Программирование приложений Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 Показывает, как создать книгу Excel и документ слова, содержащий ссылку на книге.  
  
 [Пример COM\-класса](../../../csharp/programming-guide/interop/example-com-class.md)  
 Демонстрирует, как представлять класс C\# как COM\-объект.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Пошаговое руководство. Программирование приложений Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
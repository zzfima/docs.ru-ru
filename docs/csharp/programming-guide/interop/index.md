---
title: "Взаимодействие (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5822f2e4e120f476d925520f0681055f058e3df1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="interoperability-c-programming-guide"></a>Взаимодействие (Руководство по программированию в C#)
Возможность взаимодействия позволяет использовать уже созданный неуправляемый код, экономя средства на разработку. Код, который выполняется под управлением среды CLR, называется *управляемым кодом*, а код, который выполняется вне среды CLR, называется *неуправляемым кодом*. COM, COM +, компоненты C++, компоненты ActiveX и Microsoft Win32 API являются примерами неуправляемого кода.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] обеспечивает взаимодействие с неуправляемым кодом посредством служб вызова неуправляемого кода (PInvoke), пространства имен <xref:System.Runtime.InteropServices>, COM-взаимодействия и взаимодействия с C++.  
  
## <a name="in-this-section"></a>Содержание  
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 Описывает способы взаимодействия между управляемым кодом C# и неуправляемым кодом.  
  
 [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C# 2010](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 Описывает возможности, представленные в Visual C#, которые упрощают программирование для Office.  
  
 [Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 Описывает использование индексированных свойств для доступа к свойствам COM, которые имеют параметры.  
  
 [Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 Описывает, как использовать платформу вызова служб, чтобы воспроизвести звуковой WAV-файл в операционной системе Windows.  
  
 [Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md) (Пошаговое руководство. Программирование приложений Office)  
 Описывает процесс создания книги Excel и документа Word со ссылкой на эту книгу.  
  
 [Пример COM-класса](../../../csharp/programming-guide/interop/example-com-class.md)  
 Предлагает пример предоставления класса C# в качестве COM-объекта.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Взаимодействие с неуправляемым кодом](https://msdn.microsoft.com/library/sd10k43k)  
 [Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md) (Пошаговое руководство. Программирование приложений Office)

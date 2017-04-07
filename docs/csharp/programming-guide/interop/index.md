---
title: "Взаимодействие (руководство по программированию на C#) | Документация Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 7e33ed084c560470a486ebbb25035a59ddc18565
ms.openlocfilehash: c29504e18aa716cbe106dbbe00c608fd465d9ac2
ms.lasthandoff: 03/31/2017

---
# <a name="interoperability-c-programming-guide"></a>Взаимодействие (Руководство по программированию в C#)
Возможность взаимодействия позволяет использовать уже созданный неуправляемый код, экономя средства на разработку. Код, который выполняется под управлением среды CLR, называется *управляемым кодом*, а код, который выполняется вне среды CLR, называется *неуправляемым кодом*. COM, COM +, компоненты C++, компоненты ActiveX и Microsoft Win32 API являются примерами неуправляемого кода.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] обеспечивает взаимодействие с неуправляемым кодом посредством вызова служб, пространства имен <xref:System.Runtime.InteropServices>, взаимодействия C++ и взаимодействия COM (COM interop).  
  
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
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Взаимодействие с неуправляемым кодом](https://msdn.microsoft.com/library/sd10k43k)   
 [Walkthrough: Office Programming](../../../csharp/programming-guide/interop/walkthrough-office-programming.md) (Пошаговое руководство. Программирование приложений Office)

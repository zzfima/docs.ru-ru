---
title: "COM-взаимодействие в приложениях .NET Framework (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM-взаимодействие"
  - "взаимодействие, объекты .NET Framework и COM"
  - "общие компоненты"
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# COM-взаимодействие в приложениях .NET Framework (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Если объекты COM и .NET Framework используются в одном и том же приложении, необходимо учитывать различия в расположении этих объектов в памяти.  Объект .NET Framework располагается в управляемой памяти \(т.е. в памяти, управляемой общеязыковой средой выполнения\) и может в случае необходимости быть перемещен.  COM\-объект расположен в неуправляемой памяти, и не предполагается, что он будет перемещен в другое расположение в памяти.  В [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] и [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] имеются средства для управления взаимодействием таких управляемых и неуправляемых компонентов.  Дополнительные сведения об управляемом коде содержатся в разделе [Среда CLR](../Topic/Common%20Language%20Runtime%20\(CLR\).md).  
  
 В дополнение к использованию объектов COM в приложениях .NET, использование [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] может также потребоваться для разработки объектов, доступных из неуправляемого кода через COM.  
  
 Ссылки на этой странице предоставляют подробные сведения о взаимодействии между объектами COM и .NET Framework.  
  
## Связанные подразделы  
 [COM\-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)  
 Ссылки на разделы, посвященные взаимодействию COM в Visual Basic, включая объекты COM, элементы управления ActiveX, файлы Win32 DLL, управляемые объекты и наследование объектов COM.  
  
 [COM Interop Wrapper Error](/visual-cpp/misc/com-interop-wrapper-error)  
 Описание последствий и альтернатив при невозможности создания программы\-оболочки взаимодействия COM для конкретного компонента.  
  
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)  
 Краткое описание некоторых проблем взаимодействия с управляемыми и неуправляемыми кодами и ссылки для дальнейшего изучения.  
  
 [COM Wrappers](../Topic/COM%20Wrappers.md)  
 Описание вызываемых оболочек времени выполнения, которые позволяют управляемым кодам вызывать методы COM, а также вызываемых оболочек COM, позволяющих клиентам COM вызывать методы объекта .NET.  
  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ru-ru/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Ссылки на разделы, посвященные COM\-взаимодействию, программам\-оболочкам, исключениям, наследованию, работе с потоками, событиям, преобразованиям, маршалингу.  
  
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)  
 Описание инструментария, с помощью которого можно преобразовать определения типов, найденные в библиотеке типов СОМ, в эквивалентные определения в сборках среды CLR.
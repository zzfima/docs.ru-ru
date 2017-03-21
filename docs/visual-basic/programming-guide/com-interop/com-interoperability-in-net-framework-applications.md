---
title: "COM-взаимодействие в приложениях .NET Framework (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 308ee8e495efa9368ef55d781f6b6dc314db51ac
ms.lasthandoff: 03/13/2017

---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>COM-взаимодействие в приложениях .NET Framework (Visual Basic)
Если вы хотите использовать объекты COM и .NET Framework в одном приложении, необходимо учитывать различия в расположении этих объектов в памяти. Объект .NET Framework располагается в управляемой памяти, памяти, управляемой средой CLR и при необходимости может быть перемещен средой выполнения. Объект COM располагается в неуправляемой памяти и не планируется переместить в другое расположение в памяти. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]и [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] предоставляют средства для управления взаимодействием таких управляемых и неуправляемых компонентов. Дополнительные сведения об управляемом коде см. в разделе [общеязыковая среда выполнения](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).  
  
 В дополнение к использованию объектов COM в приложениях .NET, можно также использовать [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для разработки объектов, доступных из неуправляемого кода через COM.  
  
 Ссылки на этой странице приведены сведения о взаимодействии между объектами COM и .NET Framework.  
  
## <a name="related-sections"></a>Связанные разделы  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)  
 Ссылки на разделы, посвященные взаимодействию COM в Visual Basic, включая объекты COM, элементы управления ActiveX, DLL-библиотеки Win32, управляемые объекты и наследование объектов COM.  
  
 [Ошибка оболочки COM-взаимодействия](https://docs.microsoft.com/cpp/misc/com-interop-wrapper-error)  
 Описание последствий и альтернатив при невозможности создания программы-оболочки взаимодействия COM для конкретного компонента.  
  
 [Взаимодействие с неуправляемым кодом](https://msdn.microsoft.com/library/sd10k43k)  
 Краткое описание некоторых проблем взаимодействия между управляемым и неуправляемым кодом и ссылки для дальнейшего изучения.  
  
 [Оболочки COM](http://msdn.microsoft.com/library/e56c485b-6b67-4345-8e66-fd21835a6092)  
 Описание вызываемых оболочек времени выполнения, которые позволяют управляемому коду вызывать методы COM, и вызываемых оболочек COM, позволяющих клиентам COM вызывать методы объекта .NET.  
  
 [Расширенное COM-взаимодействие](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Ссылки на разделы, посвященные COM-взаимодействию оболочки, исключения, наследования, работа с потоками, событий, преобразований и маршалинг.  
  
 [Tlbimp.exe (программа импорта библиотек типов)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 Описывает средства, которые можно использовать для преобразования определения типов, найденные в библиотеке типов COM, в эквивалентные определения сборки среды CLR.

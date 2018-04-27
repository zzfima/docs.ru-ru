---
title: COM-взаимодействие в приложениях .NET Framework (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25fbde3845d378d4a2bcfc13c71124ad1bc29514
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>COM-взаимодействие в приложениях .NET Framework (Visual Basic)
Если вы хотите использовать .NET Framework и COM-объектов в одном приложении, необходимо учитывать различия в расположении этих объектов в памяти. Объект .NET Framework располагается в управляемой памяти, памяти, управляемой средой CLR и при необходимости может быть перемещен средой выполнения. COM-объект находится в неуправляемой памяти и не планируется переместить в другое расположение в памяти. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют средства для управления взаимодействием таких управляемых и неуправляемых компонентов. Дополнительные сведения об управляемом коде см. в разделе [общеязыковая среда выполнения](../../../standard/clr.md).  
  
 В дополнение к использованию объектов COM в приложениях .NET, можно также использовать Visual Basic для разработки объектов, доступных из неуправляемого кода через COM.  
  
 Ссылки на этой странице приведены сведения о взаимодействии между объектами COM и .NET Framework.  
  
## <a name="related-sections"></a>Связанные разделы  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)  
 Ссылки на разделы, посвященные COM-взаимодействие в Visual Basic, включая объекты COM, элементы управления ActiveX, DLL-библиотеки Win32, управляемые объекты и наследование COM-объектов.  
  
 [Ошибка оболочки COM-взаимодействия](/cpp/misc/com-interop-wrapper-error)  
 Описание последствий и параметры, если система проектов не удается создать оболочку COM взаимодействия для конкретного компонента.  
  
 [Взаимодействие с неуправляемым кодом](../../../framework/interop/index.md)  
 Краткое описание некоторых проблем взаимодействия между управляемым и неуправляемым кодом и ссылки для дальнейшего изучения.  
  
 [Oболочки COM](../../../framework/interop/com-wrappers.md)  
 Описание вызываемых оболочек времени выполнения, которые позволяют управляемому коду вызывать методы COM, и вызываемых оболочек COM, которые позволяют клиентам COM вызывать методы объекта .NET.  
  
 [Расширенное COM-взаимодействие](../../../framework/interop/index.md)  
 Ссылки на разделы, посвященные оболочки, исключения, наследования, работа с потоками, событий, преобразований и маршалинг COM-взаимодействию.  
  
 [Tlbimp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 Описывает средства, которые можно использовать для преобразования определений типов, имеющихся в библиотеке типов COM, в эквивалентные определения сборки среды CLR.

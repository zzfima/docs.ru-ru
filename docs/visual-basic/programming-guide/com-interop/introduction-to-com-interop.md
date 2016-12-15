---
title: "Знакомство с COM-взаимодействием (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM-взаимодействие, сведения о COM-взаимодействии"
  - "сборки взаимодействия"
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Знакомство с COM-взаимодействием (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модель COM позволяет объекту предоставлять его функциональность другим компонентам и приложениям хоста.  Несмотря на то, что объекты COM в течение многих лет служили основой программирования в Windows, приложения, разработанные для среды CLR, имеют много преимуществ.  
  
 Приложения [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] непременно заменят в будущем приложения, разработанные с применением COM.  До этого, возможно, придется использовать или создавать объекты COM с помощью [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  Возможность взаимодействия с COM, или *COM\-взаимодействие*, позволяет использовать существующие объекты COM при постепенном переходе к [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 Используя [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] для создания компонентов COM, можно использовать COM\-взаимодействие без регистрации.  Это позволяет управлять тем, какая версия DLL включена, когда более чем одной версии установлено на компьютере, и позволяет конечным пользователям использовать XCOPY или FTP, чтобы скопировать приложение в соответствующий каталог на своем компьютере, где его можно запустить.  Дополнительные сведения см. в разделе [Registration\-Free COM Interop](../Topic/Registration-Free%20COM%20Interop.md).  
  
## Управляемый код и данные  
 Код, разработанный для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] *управляемого кода*, содержит метаданные, которые используются средой CLR.  Данные, используемые приложениями [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], называют *управляемыми данными*, так как среда выполнения управляет задачами, связанными с данными, такими как выделение и освобождение памяти и проверка типов.  По умолчанию [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] использует управляемый код и данные, но можно получить доступ к неуправляемому коду и данным объектов COM при помощи сборок взаимодействия \(описываемых далее на этой странице\).  
  
## сборкам.  
 Сборка является основным стандартным блоком [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложения.  Это коллекция функциональных элементов, которые уже созданы, обновлены и развернуты как отдельный модуль реализации, содержащий один или несколько файлов.  В каждой сборке содержится манифест сборки.  
  
## Библиотеки типов и манифесты сборок  
 Библиотеки типов описывают характеристики объектов COM, такие как имена членов и типы данных.  Манифесты сборки выполняют аналогичную функцию для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложений.  Они включают сведения о следующем:  
  
-   Идентификация сборки, версия, язык и региональные параметры, цифровая подпись.  
  
-   Файлы, формирующие реализацию сборки.  
  
-   Типы и ресурсы, образующие сборку.  Они включают то, что экспортируется из нее.  
  
-   Зависимости от других сборок во время компиляции.  
  
-   Разрешения, необходимые сборке для правильного запуска  
  
 Дополнительные сведения о сборках и манифестах сборки содержатся в разделе [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
### Импорт и экспорт библиотек типов  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] содержит программу Tlbimp, которая позволяет импортировать информацию из библиотеки типов в приложение [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Можно создавать библиотеки типов из сборок при помощи программы Tlbexp.  
  
 Сведения о Tlbimp и Tlbexp содержатся в [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md) [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md).  
  
## Сборки взаимодействия  
 Сборки взаимодействия являются сборками [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], которые действуют как мост между управляемым и неуправляемым кодом, отображая члены объекта COM эквивалентными управляемым членам [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Сборки взаимодействия, созданные [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], управляют многими деталями работы с объектами COM, например маршалингом взаимодействия.  
  
## Маршалинг взаимодействия  
 Все приложения [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] используют набор общих типов, что позволяет объектам взаимодействовать независимо от используемого языка программирования.  Параметры и возвращаемые значения объектов COM иногда используют типы данных, которые отличаются от используемых в управляемом коде.  *Маршалинг взаимодействия* — это процесс упаковки параметров и возвращения значений в эквивалентных типах данных при передаче в объекты COM и получении из объектов COM.  Дополнительные сведения см. в разделе [Interop Marshaling](../Topic/Interop%20Marshaling.md).  
  
## См. также  
 [COM\-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Пошаговое руководство. Реализация наследования с использованием COM\-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Interop Marshaling](../Topic/Interop%20Marshaling.md)   
 [Registration\-Free COM Interop](../Topic/Registration-Free%20COM%20Interop.md)
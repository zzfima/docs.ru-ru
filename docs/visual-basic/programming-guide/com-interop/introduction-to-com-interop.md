---
title: "Знакомство с COM-взаимодействием (Visual Basic) | Документы Microsoft"
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
- interop assemblies
- COM interop, about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 8866dbadca040c57ed2b59540dd2c341eb81758c
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-com-interop-visual-basic"></a>Знакомство с COM-взаимодействием (Visual Basic)
Модель компонентных объектов (COM) позволяет объекту предоставлять его функциональность другим компонентам и приложениям хоста. Хотя COM-объекты были основой программирования в течение многих лет в Windows, приложений, предназначенных для общеязыковой среды выполнения (CLR), имеют много преимуществ.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]приложения будут заменят разработанные с применением COM. До этого, может потребоваться использовать или создавать объекты COM с помощью [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]. Взаимодействие с COM, или *COM-взаимодействия*, позволяет использовать существующие объекты COM при постепенном переходе [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] в своем темпе.  
  
 С помощью [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] для создания компонентов COM, можно использовать COM-взаимодействие без регистрации. Это позволяет контролировать, какая версия DLL включена, при более чем одной версии установлено на компьютере и позволяет конечным пользователям использовать XCOPY или FTP скопировать приложение в соответствующий каталог на своем компьютере когда может быть выполнена. Дополнительные сведения см. в разделе [COM-взаимодействия без регистрации](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Управляемый код и данные  
 Код, разработанный для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] называется *управляемого кода*и содержит метаданные, которые используются средой CLR. Данные, используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложения называется *управляемыми данными* , так как среда выполнения управляет задачами, связанными с данными, такие как выделение и освобождение памяти и проверка типов. По умолчанию [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] использует управляемый код и данные, но можно получить доступ к неуправляемому коду и данным объектов COM с помощью сборок взаимодействия (описываемых далее на этой странице).  
  
## <a name="assemblies"></a>Сборки  
 Сборка является основным стандартным блоком [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложения. Это коллекция функциональных возможностей, которые построен, версии и развертываются как единое одной реализации, содержащий один или несколько файлов. Каждая сборка содержит манифест сборки.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Библиотеки типов и манифесты сборки  
 Библиотеки типов описывают характеристики объектов COM, такие как имена членов и типы данных. Манифесты сборки выполняют ту же функцию для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложений. В их число входят следующие сведения:  
  
-   Идентификатор сборки, версии, языка и региональных параметров и цифровой подписи.  
  
-   Файлов, составляющих реализацию сборки.  
  
-   Типы и ресурсы, образующие сборку. Сюда входят те, которые экспортируются из него.  
  
-   Во время компиляции зависимости от других сборок.  
  
-   Разрешения, необходимые для правильного выполнения сборки.  
  
 Дополнительные сведения о сборках и манифестах сборки см. в разделе [сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Импорт и экспорт библиотек типов  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]содержит программу Tlbimp, которая позволяет импортировать информацию из библиотеки типов в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложения. Можно создавать библиотеки типов из сборок при помощи программы Tlbexp.  
  
 Сведения о программе Tlbimp и Tlbexp содержатся [Tlbimp.exe (программа импорта библиотек типов)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) и [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Сборки взаимодействия  
 Сборки взаимодействия являются [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки, которые мост между управляемым и неуправляемым кода, отображая члены объекта COM в эквивалент [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] управляемых элементов. Сборки взаимодействия, созданные [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] обрабатывать различные аспекты работы с объектами COM, например маршалингом взаимодействия.  
  
## <a name="interoperability-marshaling"></a>Маршалинг взаимодействия  
 Все [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложения используют набор общих типов, обеспечить взаимодействие объектов, независимо от используемого языка программирования. Параметры и возвращаемые значения объектов COM иногда используют типы данных, которые отличаются от используемых в управляемом коде. *Маршалинг взаимодействия* — это процесс упаковки параметров и возвращения значений в эквивалентных типах данных при передаче в объекты COM и обратно. Дополнительные сведения см. в разделе [маршалинг взаимодействия](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Взаимодействие с неуправляемым кодом](https://msdn.microsoft.com/library/sd10k43k)   
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Tlbimp.exe (программа импорта библиотек типов)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Маршалинг взаимодействия](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a)   
 [Без регистрации COM-взаимодействия](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)

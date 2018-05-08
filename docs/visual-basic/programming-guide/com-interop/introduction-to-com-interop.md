---
title: Знакомство с COM-взаимодействием (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 639b621215f25bc1042274a92a21fca2985e5918
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-com-interop-visual-basic"></a>Знакомство с COM-взаимодействием (Visual Basic)
Модель объектов компонентов (COM) позволяет объекту предоставлять его функциональность другим компонентам и приложениям хоста. Хотя COM-объекты были основой программирования в течение многих лет в Windows, приложений, предназначенных для общеязыковой среды выполнения (CLR), имеют много преимуществ.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения будут заменят разработанные с применением COM. До этого времени может потребоваться использовать или создавать объекты COM с помощью Visual Studio. Взаимодействие с COM, или *COM-взаимодействия*, позволяет использовать существующие объекты COM при постепенном переходе [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] в своем темпе.  
  
 С помощью [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] для создания компонентов COM, можно использовать COM-взаимодействие без регистрации. Это позволяет контролировать, какая версия библиотеки DLL будет включаться при более чем одной версии установлена на компьютере и позволяет конечным пользователям использовать XCOPY или FTP скопировать приложение в соответствующий каталог на своем компьютере когда может быть выполнена. Дополнительные сведения см. в разделе [COM-взаимодействия без регистрации](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Управляемый код и данные  
 Код, разработанный для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] называется *управляемого кода*и содержит метаданные, используемые средой CLR. Данные, используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения называется *управляемыми данными* так, как среда выполнения управляет задач, связанных с данными, такие как выделение и освобождение памяти и проверка типов. По умолчанию Visual Basic .NET использует управляемый код и данные, но можно получить доступ к неуправляемому коду и данным объектов COM с помощью сборок взаимодействия (описанным ниже на этой странице).  
  
## <a name="assemblies"></a>Сборки  
 Сборка является основной строительный блок [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения. Это коллекция функциональных возможностей, построенные с версией и развертываются как единое реализаций, содержащий один или несколько файлов. Каждая сборка содержит манифест сборки.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Библиотеки типов и манифесты сборки  
 Библиотеки типов описывают характеристики объектов COM, такие как имена членов и типов данных. Манифесты сборки выполняют ту же функцию для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложений. Они включают следующие сведения:  
  
-   Удостоверение сборки, версию, язык и региональные параметры и цифровой подписи.  
  
-   Файлы, образующие реализацию сборки.  
  
-   Типы и ресурсы, составляющие сборку. Сюда входят те, которые экспортируются из него.  
  
-   Во время компиляции зависимостей от других сборок.  
  
-   Разрешения, необходимые для сборки, для правильной работы.  
  
 Дополнительные сведения о сборках и манифестов сборки см. в разделе [сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Импорт и экспорт библиотеки типов  
 Visual Studio содержит программу Tlbimp, которая позволяет импортировать информацию из библиотеки типов в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения. Можно создавать библиотеки типов из сборки с помощью программы Tlbexp.  
  
 Сведения о Tlbimp и Tlbexp см. в разделе [Tlbimp.exe (программа импорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md) и [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Сборки взаимодействия  
 Сборки взаимодействия являются [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки, которые мост между управляемым и неуправляемым кода, отображая члены объекта COM, в эквивалент [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] управляемых элементов. Сборки взаимодействия, созданные в Visual Basic .NET обрабатывать различные аспекты работы с объектами COM, такие как маршалинг взаимодействия.  
  
## <a name="interoperability-marshaling"></a>Маршалинг взаимодействия  
 Все [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения используют набор общих типов, обеспечить взаимодействие объектов, независимо от используемого языка программирования. Параметры и возвращаемые значения объектов COM иногда используют типы данных, которые отличаются от тех, которые используются в управляемом коде. *Маршалинг взаимодействия* — это процесс упаковки параметров и возвращаемых значений в эквивалентные типы данных при передаче и COM-объектов. Дополнительные сведения см. в разделе [маршалинг взаимодействия](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>См. также  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Пошаговое руководство. Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Взаимодействие с неуправляемым кодом](../../../framework/interop/index.md)  
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Tlbimp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Маршалинг взаимодействия](../../../framework/interop/interop-marshaling.md)  
 [COM-взаимодействие без регистрации](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)

---
title: Знакомство с COM-взаимодействием (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 1eebdf4bee09f2a568092f275b57416c3def9ebc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624818"
---
# <a name="introduction-to-com-interop-visual-basic"></a>Знакомство с COM-взаимодействием (Visual Basic)
Модель объектов компонентов (COM) позволяет объекту предоставлять свою функциональность другим компонентам и ведущим приложениям. Хотя COM-объектов, стали основой для Windows, программирования в течение многих лет, приложений, предназначенных для общеязыковой среды выполнения (CLR) предоставляют множество преимуществ.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения будут заменят, разработанные с использованием модели COM. До этого времени может потребоваться использовать или создать COM-объектов с помощью Visual Studio. Взаимодействие с COM, или *COM-взаимодействия*, позволяет использовать существующие COM-объекты при переходе к [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] в своем собственном темпе.  
  
 С помощью [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] для создания COM-компонентов, можно использовать COM-взаимодействия без регистрации. Это дает возможность контролировать, какая версия DLL включена в том случае, если более одной версии устанавливается на компьютере и позволяет конечным пользователям использовать XCOPY или FTP скопировать приложение в соответствующий каталог на своем компьютере где ее можно запустить. Дополнительные сведения см. в разделе [COM-взаимодействия без регистрации](../../../framework/interop/registration-free-com-interop.md).  
  
## <a name="managed-code-and-data"></a>Управляемый код и данные  
 Код, разработанный для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] называется *управляемого кода*и содержит метаданные, используемые средой CLR. Данные, используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложений называется *данных управляемых* так, как среда выполнения управляет задачи, связанные с данными, такие как выделение и освобождение памяти и проверка типов. По умолчанию Visual Basic .NET использует управляемый код и данные, но можно получить доступ к неуправляемому коду, а также данные COM-объектов с помощью сборок взаимодействия (описанным ниже на этой странице).  
  
## <a name="assemblies"></a>Сборки  
 Сборка является основной строительный блок [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения. Это коллекция функций, построенный с контролем версий и развертываются как единое единую реализацию, содержащий один или несколько файлов. Каждая сборка содержит манифест сборки.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Библиотеки типов и манифестов сборки  
 Библиотеки типов описывают характеристики объектов COM, таких как имена элементов и типов данных. Манифесты сборки выполняют ту же функцию для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложений. К ним относятся следующие сведения:  
  
- Удостоверение сборки, версию, язык и региональные параметры и цифровой подписи.  
  
- Файлы, составляющих реализацию сборки.  
  
- Типов и ресурсов, входящих в сборку. Сюда входят те, которые экспортируются из него.  
  
- Во время компиляции зависимости от других сборок.  
  
- Разрешения, необходимые для сборки для правильной работы.  
  
 Дополнительные сведения о сборках и манифестов сборки см. в разделе [сборок в .NET](../../../standard/assembly/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Импорт и экспорт библиотеки типов  
 Visual Studio содержит программу Tlbimp, которая позволяет импортировать информацию из библиотеки типов в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения. Можно создавать библиотеки типов из сборки с помощью программы Tlbexp.  
  
 Сведения о Tlbimp и Tlbexp, см. в разделе [Tlbimp.exe (программа импорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md) и [Tlbexp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).  
  
## <a name="interop-assemblies"></a>Сборки взаимодействия  
 Сборки взаимодействия являются [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки, мост между управляемым и неуправляемым кода, отображая члены объекта COM в эквивалент [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] управляемых элементов. Сборки взаимодействия, созданные в Visual Basic .NET обрабатывать большую часть особенностей работы с объектами COM, такие как маршалинг взаимодействия.  
  
## <a name="interoperability-marshaling"></a>Маршалинг взаимодействия  
 Все [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложений совместно используют набор общих типы, обеспечивающие взаимодействие объектов, независимо от языка программирования, который используется. Параметры и возвращаемые значения объектов COM иногда используют типы данных, которые отличаются от тех, которые используются в управляемом коде. *Маршалинг взаимодействия* — это процесс упаковки параметров и возвращаемых значений в эквивалентные типы данных при передаче и из COM-объектов. Дополнительные сведения см. в разделе [маршалинг взаимодействия](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>См. также

- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
- [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Взаимодействие с неуправляемым кодом](../../../framework/interop/index.md)
- [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Tlbimp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Маршалинг взаимодействия](../../../framework/interop/interop-marshaling.md)
- [COM-взаимодействие без регистрации](../../../framework/interop/registration-free-com-interop.md)

---
title: Практическое руководство. Поиск сборок с помощью DEVPATH
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 6fa864f814d6a9ce04f2bce92c61cd0075ab5145
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912999"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Практическое руководство. Поиск сборок с помощью DEVPATH
Разработчикам может потребоваться убедиться, что создаваемая ими общая сборка работает правильно с несколькими приложениями. Вместо постоянного размещения сборки в глобальном кэше сборок во время цикла разработки разработчик может создать переменную среды DEVPATH, которая указывает на выходной каталог сборки для сборки.  
  
 Например, предположим, что создается общая сборка с именем Мишаредассембли, а выходной каталог — К:\мишаредассембли\дебуг. К:\мишаредассембли\дебуг можно разместить в переменной DEVPATH. Затем необходимо указать [ \<элемент > developmentMode](./file-schema/runtime/developmentmode-element.md) в файле конфигурации компьютера. Этот элемент указывает среде CLR использовать DEVPATH для нахождение сборок.  
  
 Общая сборка должна быть обнаружена средой выполнения.  Чтобы указать частный каталог для разрешения ссылок на сборки, используйте [ \<элемент CodeBase > Element](./file-schema/runtime/codebase-element.md) или [ \<зондированию >](./file-schema/runtime/probing-element.md) в файле конфигурации, как описано в разделе [Указание расположения сборки](specify-assembly-location.md).  Также можно разместить сборку в подкаталоге каталога приложения. Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
> Это дополнительная функция, предназначенная только для разработки.  
  
 В следующем примере показано, как заставить среду выполнения искать сборки в каталогах, заданных переменной среды DEVPATH.  
  
## <a name="example"></a>Пример  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 По умолчанию этот параметр имеет значение false.  
  
> [!NOTE]
> Используйте этот параметр только во время разработки. Среда выполнения не проверяет версии сборок со строгими именами, найденных в DEVPATH. Он просто использует первую найденную сборку.  
  
## <a name="see-also"></a>См. также

- [Настройка приложений с помощью файлов конфигурации](index.md)

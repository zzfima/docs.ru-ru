---
title: "Практическое руководство. Поиск сборок с помощью DEVPATH"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 70448f7ce4c00274dde14bace603e5c8852bf148
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Практическое руководство. Поиск сборок с помощью DEVPATH
Разработчикам может потребоваться убедитесь в том, что общей сборки, которые они построении правильно работает с несколькими приложениями. Вместо постоянно помещать сборку в глобальный кэш сборок во время цикла разработки, разработчик может создать переменную среды DEVPATH, которая указывает выходной каталог сборки для сборки.  
  
 Например предположим, что вы создаете общей сборки с именем MySharedAssembly и в выходной каталог C:\MySharedAssembly\Debug. C:\MySharedAssembly\Debug можно поместить в переменной DEVPATH. Необходимо указать [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) элемент в файле конфигурации компьютера. Этот элемент предписывает среда использовать DEVPATH для обнаружения сборок.  
  
 Эту сборку необходимо обнаруживаемый средой выполнения.  Чтобы указать закрытый каталог для разрешения использования ссылок на сборки [ \<codeBase > элемент](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) или [ \<зондирования > элемент](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) в файле конфигурации, как описано в [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).  Можно также поместить сборку в подкаталог в каталоге приложения. Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Это дополнительная функция, предназначенная только для разработки.  
  
 В следующем примере показано, как среда выполнения поиска сборок в каталогах, указанных в переменной среды DEVPATH.  
  
## <a name="example"></a>Пример  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 Этот параметр по умолчанию используется значение false.  
  
> [!NOTE]
>  Используйте этот параметр только во время разработки. Среда выполнения проверяет версии сборок со строгими именами, в DEVPATH. Он просто использует первый найденную сборку.  
  
## <a name="see-also"></a>См. также  
 [Настройка приложений .NET Framework](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)

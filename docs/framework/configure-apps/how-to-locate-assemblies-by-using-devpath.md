---
title: Как выполнить Поиск сборок с помощью DEVPATH
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 11ed84b01adf57eb526eaa1e71c6968e48c64cc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627554"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Как выполнить Поиск сборок с помощью DEVPATH
Разработчикам может потребоваться, общая сборка, которую они создадут правильно работает с несколькими приложениями. Вместо постоянно помещать сборку в глобальный кэш сборок во время цикла разработки, разработчик может создать переменной среды DEVPATH, которая указывает выходной каталог сборки для сборки.  
  
 Например предположим, что вы создаете вызывается MySharedAssembly общей сборки и в выходной каталог C:\MySharedAssembly\Debug. C:\MySharedAssembly\Debug можно поместить в переменную DEVPATH. Необходимо указать [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) элемент в файле конфигурации компьютера. Этот элемент указывает среда CLR нужно использовать DEVPATH для поиска сборок.  
  
 Общая сборка должна быть обнаруживаема среды выполнения.  Для указания закрытого каталога для разрешения использования ссылок на сборки [ \<codeBase > элемент](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) или [ \<probing > элемент](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) в файле конфигурации, как описано в разделе [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).  Можно также поместить сборку в подкаталоге каталога приложения. Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Это расширенная функция, предназначенная только для разработки.  
  
 В следующем примере показано, как среда выполнения для поиска сборок в каталогах, указанных в переменной среды DEVPATH.  
  
## <a name="example"></a>Пример  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 Этот параметр по умолчанию false.  
  
> [!NOTE]
>  Используйте этот параметр только во время разработки. Среда выполнения не проверяет версии на в DEVPATH сборок со строгим именем. Он просто использует первый найденную сборку.  
  
## <a name="see-also"></a>См. также
- [Настройка приложений .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)

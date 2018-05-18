---
title: Миграция из .NET Framework 1.1
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc181d0aecd6a0c7c0800544ea00a818573c954c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-from-the-net-framework-11"></a>Миграция из .NET Framework 1.1
[!INCLUDE[win7](../../../includes/win7-md.md)] и более поздние версии операционной системы Windows не поддерживают [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)]. Поэтому приложения, предназначенные для [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] , не будут запускаться в [!INCLUDE[win7](../../../includes/win7-md.md)] или более поздних версиях операционной системы без внесения изменений. В этой статье рассматриваются действия, которые нужно выполнить для запуска приложения, предназначенного для [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)], в [!INCLUDE[win7](../../../includes/win7-md.md)] или более поздней версии операционной системы Windows. Дополнительные сведения о [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] и [!INCLUDE[win8](../../../includes/win8-md.md)] см. в статье [Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10](../../../docs/framework/install/run-net-framework-1-1-apps.md).  
  
## <a name="retargeting-or-recompiling"></a>Переназначение и перекомпиляция  
 Есть два способа обеспечить запуск приложения, которое было скомпилировано с использованием [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] , в [!INCLUDE[win7](../../../includes/win7-md.md)] или более поздней версии операционной системы Windows.  
  
-   Можно перенацелить приложение для запуска в платформе [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Для изменения целевой платформы необходимо добавить в файл конфигурации приложения элемент [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md), который позволит приложению запускаться в платформе [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Такой файл конфигурации имеет следующий вид:  
  
    ```xml  
    <configuration>   
       <startup>  
          <supportedRuntime version="v4.0"/>  
       </startup>  
    </configuration>  
    ```  
  
-   Можно перекомпилировать приложение с помощью компилятора, предназначенного для [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Если для разработки и компиляции решения первоначально использовалась среда Visual Studio 2003, можно открыть решение в среде [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] и использовать диалоговое окно **Совместимость проекта** для конвертации решения и файлов проекта из форматов, используемых Visual Studio 2003, в формат Microsoft Build Engine (MSBuild), используемый средой [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)].  
  
 Независимо от того, перекомпилируется ли или перенацеливается приложение, необходимо определить, затронуто ли оно какими-либо изменениями, введенными в более поздних версиях платформы .NET Framework. Эти изменения могут быть двух типов:  
  
-   критические изменения, введенные в более поздних относительно [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] версиях платформы .NET Framework;  
  
-   отметка типов и членов типов как нерекомендуемых или устаревших в более поздних относительно [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] версиях платформы .NET Framework.  
  
 Независимо от того, перенацеливается ли или перекомпилируется приложение, необходимо просмотреть как критические изменения, так и устаревшие типы и члены для каждой версии платформы .NET Framework, выпущенной после [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)].  
  
## <a name="breaking-changes"></a>Критические изменения  
 Когда происходит критическое изменение, обходной путь может быть доступен как для перенацеленных, так и для перекомпилированных приложений (в зависимости от конкретного изменения). В некоторых случаях для восстановления предыдущего поведения в элемент [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) файла конфигурации приложения можно добавить дочерний элемент. Например, следующий файл конфигурации восстанавливает режим сортировки и сравнения строк, используемый в [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)], и может применяться с перенацеленным или перекомпилированным приложением.  
  
```xml  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
 Однако в некоторых случаях может потребоваться изменить исходный код и перекомпилировать приложение.  
  
 Чтобы оценить влияние возможных критических изменений на приложение, необходимо просмотреть следующие списки изменений.  
  
-   В документе[Критические изменения в .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkId=125263) перечислены изменения, внесенные в [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] , которые могут повлиять на приложение, предназначенное для [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)].  
  
-   В документе[Изменения в .NET Framework 3.5 SP1](http://go.microsoft.com/fwlink/?LinkID=186989) перечислены различия между [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)].  
  
-   В документе о [проблемах при миграции на .NET Framework 4](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md) перечислены различия между [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] и [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
## <a name="obsolete-types-and-members"></a>Устаревшие типы и члены  
 Нерекомендуемые типы и члены несколько по-разному влияют на перенацеленные и перекомпилированные приложения. Устаревший тип или член не будет влиять на перенацеленное приложение, если он физически не удален из его сборки. При перекомпиляции приложения, в котором используются устаревшие типы или члены, обычно появляется предупреждение компилятора, а не ошибка. Однако в некоторых случаях при такой перекомпиляции возникает ошибка компилятора, и код, в котором используется устаревший тип или член, не компилируется успешно. В этом случае перед перекомпиляцией приложения необходимо переписать исходный код, в котором вызывается устаревший тип или член. Дополнительные сведения об устаревших типах и членах см. в статье [Устаревшие классы библиотеки классов](../../../docs/framework/whats-new/whats-obsolete.md).  
  
 Чтобы оценить влияние типов и членов, не рекомендованных к использованию после выпуска [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)], см. статью [Устаревшие классы библиотеки классов](../../../docs/framework/whats-new/whats-obsolete.md). Просмотрите списки устаревших типов и членов для [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)], [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].

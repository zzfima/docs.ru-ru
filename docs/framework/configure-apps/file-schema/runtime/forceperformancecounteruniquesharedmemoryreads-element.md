---
title: Элемент <forcePerformanceCounterUniqueSharedMemoryReads>
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26fed0a10b9a25f25a580c7ac9a468cbedeb3671
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489469"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads > элемент
Указывает, использует ли файл PerfCounter.dll параметр реестра CategoryOptions в приложении .NET Framework версии 1.1, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.  
  
 \<configuration>  
\<Среда выполнения >  
\<forcePerformanceCounterUniqueSharedMemoryReads >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, использует ли файл PerfCounter.dll параметр реестра, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|PerfCounter.dll не использует параметр реестра, установка этого параметра значение по умолчанию.|  
|`true`|PerfCounter.dll используйте PerfCounter.dll параметр реестра.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 В версиях .NET Framework до .NET Framework 4 версия PerfCounter.dll, который был загружен предоставивших в среду выполнения, который был загружен в процессе. Если компьютер имеет оба в .NET Framework версии 1.1 и [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] установки приложения .NET Framework 1.1 будет загрузки версии .NET Framework 1.1 PerfCounter.dll. Начиная с .NET Framework 4, загружается последняя установленная версия PerfCounter.dll. Это означает, что приложения .NET Framework 1.1 загрузит PerfCounter.dll версии .NET Framework 4, если .NET Framework 4 установлена на компьютере.  
  
 Начиная с .NET Framework 4, при использовании счетчиков производительности, PerfCounter.dll проверяет запись реестра CategoryOptions для каждого поставщика, чтобы определить, следует ли чтение из общей памяти конкретной категории или глобальной общей памяти. .NET Framework 1.1 PerfCounter.dll не поддерживает эту запись реестра, так как он не учитывает общей памяти конкретной категории; он считывает из глобальную общую память.  
  
 Для обеспечения обратной совместимости .NET Framework 4 PerfCounter.dll не проверяет запись реестра CategoryOptions при работе в приложении .NET Framework 1.1. Он просто использует глобальную общую память, так же, как .NET Framework 1.1 PerfCounter.dll. Тем не менее, вы можете сообщить о .NET Framework 4 PerfCounter.dll для проверки параметра реестра, включив `<forcePerformanceCounterUniqueSharedMemoryReads>` элемент.  
  
> [!NOTE]
>  Включение `<forcePerformanceCounterUniqueSharedMemoryReads>` элемент не гарантирует, что будет использоваться общей памяти конкретной категории. Параметр включен для `true` только вызывает PerfCounter.dll параметр реестра CategoryOptions ссылок. Параметр по умолчанию является использование общей памяти конкретной категории; Тем не менее можно изменить параметр, чтобы указать, что следует использовать глобальную общую память.  
  
 Раздел реестра, который содержит параметр CategoryOptions является HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance. По умолчанию параметр имеет значение 3, предписывающее PerfCounter.dll для использования общей памяти конкретной категории. Если параметр имеет значение 0, PerfCounter.dll использует глобальную общую память. Данные экземпляра будет использоваться повторно, только в том случае, если имя экземпляра не идентичен используемому экземпляру. Все версии будут иметь возможность записи в категорию. Если параметр имеет значение 1, использовать глобальную общую память, но данные экземпляра можно использовать повторно, если имя категории, имеют одинаковую длину категорию используются повторно.  
  
 Параметры 0 и 1 может привести к утечке памяти и заполнению памяти счетчиков производительности.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как указать, что PerfCounter.dll должны ссылаться реестра CategoryOptions, чтобы определить, какой сериализатор следует использовать общей памяти конкретной категории.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
title: Элемент <forcePerformanceCounterUniqueSharedMemoryReads>
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154144"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> Элемент
Указывает, использует ли файл PerfCounter.dll параметр реестра CategoryOptions в приложении .NET Framework версии 1.1, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, использует ли PerfCounter.dll настройки реестра CategoryOptions для определения того, следует ли загружать данные счетчика производительности из общей памяти, специфичной для категории, или глобальной памяти.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|PerfCounter.dll не использует настройки реестра CategoryOptions Это по умолчанию.|  
|`true`|PerfCounter.dll использует настройки реестра CategoryOptions.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 В версиях рамочного соглашения .NET перед .NET Framework 4 загруженная версия PerfCounter.dll соответствовала времени выполнения, загруженного в процессе. Если бы компьютер установил как версию .NET Framework 1.1, так и .NET Framework 2.0, приложение .NET Framework 1.1 загрузило бы версию PerfCounter.dll .NET Framework 1.1. Начиная с .NET Framework 4, загружается новейшая установленная версия PerfCounter.dll. Это означает, что приложение .NET Framework 1.1 загрузит версию PerfCounter.dll .NET Framework 4, если на компьютере будет установлена система .NET Framework 4.  
  
 Начиная с .NET Framework 4, perfCounter.dll проверяет вход в реестр CategoryOptions для каждого поставщика, чтобы определить, следует ли читать из общей памяти, специфичная для категории, или глобальной общей памяти. В .NET Framework 1.1 PerfCounter.dll не читает сярвод, поскольку он не знает об общей памяти, специфичном для категории; он всегда читает из глобальной общей памяти.  
  
 Для обратной совместимости,в .NET Framework 4 PerfCounter.dll не проверяет вход в реестр CategoryOptions при запуске в приложении .NET Framework 1.1. Он просто использует глобальную общую память, как и .NET Framework 1.1 PerfCounter.dll. Тем не менее, вы можете поручить .NET Framework 4 PerfCounter.dll проверить настройки реестра, включив `<forcePerformanceCounterUniqueSharedMemoryReads>` элемент.  
  
> [!NOTE]
> Включение `<forcePerformanceCounterUniqueSharedMemoryReads>` элемента не гарантирует использования общей памяти, относясь к категории. Установка включена `true` только вызывает PerfCounter.dll ссылаться на настройки реестра CategoryOptions. Настройка по умолчанию для CategoryOptions заключается в использовании общей памяти, специфичной для категории; однако можно изменить варианты категории, чтобы указать, что глобальная общая память должна использоваться.  
  
 Ключ реестра, содержащий настройки CategoryOptions, является HKEY_LOCAL_MACHINE »Система»-ТекущийКонтрольSet»Услуги\\<категорииName\>«Производительность». По умолчанию категорияOptions устанавливается до 3, что инструктирует PerfCounter.dll использовать общую память, специфичную для категории. Если категорияOptions установлена до 0, PerfCounter.dll использует глобальную общую память. Данные экземпляра будут повторно использоваться только в том случае, если имя создаваемого экземпляра идентично повторноиспользуемому экземпляру. Все версии смогут писать в категорию. Если категорияOptions установлена до 1, используется глобальная общая память, но данные экземпляра могут быть использованы повторно, если имя категории имеет такую же длину, как и повторно используемая категория.  
  
 Настройки 0 и 1 могут привести к утечке памяти и заполнению памяти счетчика производительности.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что PerfCounter.dll должен ссылаться на вход в реестр CategoryOptions, чтобы определить, следует ли использовать общую память категории.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)

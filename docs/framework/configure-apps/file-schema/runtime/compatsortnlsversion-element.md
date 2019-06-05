---
title: Элемент <CompatSortNLSVersion>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b426eaaa2dab4d54ea4c82483c079428f3bfac57
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689908"
---
# <a name="compatsortnlsversion-element"></a>\<CompatSortNLSVersion > элемент
Указывает, что при операциях сравнения строк среда выполнения должна использовать устаревший порядок сортировки.  
  
 \<configuration>  
\<Среда выполнения >  
\<CompatSortNLSVersion > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает код языка, порядок сортировки которого должен использоваться.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|4096|Код языка, представляющий альтернативный порядок сортировки. В этом случае 4096 представляет порядок сортировки для .NET Framework 3.5 и более ранних версий.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Поскольку сравнения строк, сортировки и операций регистр выполняется с <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> классов в платформе .NET Framework 4 соответствуют стандарту Unicode 5.1, результаты методы сравнения строк такие как <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> и <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> может отличаться от предыдущих версий платформы .NET Framework. Если ваше приложение зависит от устаревшее поведение, вы можете восстановить, сравнение и сортировка строк правил, используемых в .NET Framework 3.5 и более ранних версий, включая `<CompatSortNLSVersion>` элемент в файле конфигурации приложения.  
  
> [!IMPORTANT]
>  Для восстановления устаревших правил сравнения и сортировки строк также требуется, чтобы в локальной системе была доступна библиотека динамической компоновки sort00001000.dll.  
  
 Устаревшие правила сортировки и сравнения строк можно также использовать в конкретном домене приложения, передав при создании этого домена строку "NetFx40_Legacy20SortingBehavior" в метод <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере создаются экземпляры двух объектов <xref:System.String> и вызывается метод <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>, чтобы сравнить их с использованием соглашений текущих языка и региональных параметров.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 При запуске примера в .NET Framework 4, отображается следующий результат.  
  
```  
sta follows a in the sort order.  
```  
  
 Это полностью отличаются от выходных данных, которое отображается при запуске примера в .NET Framework 3.5.  
  
```  
sta equals a in the sort order.  
```  
  
 Тем не менее если добавить следующий файл конфигурации в каталог примеров и затем запустить пример в .NET Framework 4, выходные данные идентичны данным, созданным примером при его запуске в .NET Framework 3.5.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)

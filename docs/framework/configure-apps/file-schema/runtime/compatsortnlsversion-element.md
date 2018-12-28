---
title: '&lt;CompatSortNLSVersion&gt; элемент'
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
ms.openlocfilehash: a9d505dd7433978e3a5908757a1d9569fe31f49b
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614419"
---
# <a name="ltcompatsortnlsversiongt-element"></a>&lt;CompatSortNLSVersion&gt; элемент
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
  
|Значение|Описание:|  
|-----------|-----------------|  
|4096|Код языка, представляющий альтернативный порядок сортировки. В этом случае 4096 представляет порядок сортировки [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] и более ранних версий.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Поскольку сравнения строк, сортировки и операций регистр выполняется с <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> в класс [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] соответствуют стандарту Unicode 5.1, результаты методы сравнения строк, таких как <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> и <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> может отличаться от предыдущих версий платформы .NET Framework. Если приложение зависит от устаревшего поведения, можно восстановить правила сравнения и сортировки строк, используемые в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] и более ранних версиях, включив в файл конфигурации приложения элемент `<CompatSortNLSVersion>`.  
  
> [!IMPORTANT]
>  Для восстановления устаревших правил сравнения и сортировки строк также требуется, чтобы в локальной системе была доступна библиотека динамической компоновки sort00001000.dll.  
  
 Устаревшие правила сортировки и сравнения строк можно также использовать в конкретном домене приложения, передав при создании этого домена строку "NetFx40_Legacy20SortingBehavior" в метод <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере создаются экземпляры двух объектов <xref:System.String> и вызывается метод <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>, чтобы сравнить их с использованием соглашений текущих языка и региональных параметров.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 При запуске примера в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] отображаются следующие выходные данные.  
  
```  
sta follows a in the sort order.  
```  
  
 Они полностью отличаются от выходных данных, отображаемых при запуске примера в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```  
sta equals a in the sort order.  
```  
  
 Однако если в каталог примера добавить представленный ниже файл конфигурации и запустить пример в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], выходные данные будут идентичны данным, созданным примером при его запуске в [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
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

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
ms.openlocfilehash: f13265e2056c8eca62cd510154dd7c096eeabb00
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117682"
---
# <a name="compatsortnlsversion-element"></a>\<Компатсортнлсверсион > элемент
Указывает, что при операциях сравнения строк среда выполнения должна использовать устаревший порядок сортировки.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<компатсортнлсверсион >**  
  
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
  
|значения|Описание|  
|-----------|-----------------|  
|4096|Код языка, представляющий альтернативный порядок сортировки. В этом случае 4096 представляет порядок сортировки .NET Framework 3,5 и более ранних версий.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Заметки  
 Поскольку операции сравнения строк, сортировки и учета регистра, выполняемые классом <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> в .NET Framework 4, соответствуют стандарту Unicode 5,1, результаты методов сравнения строк, таких как <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> и <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType>, могут отличаться от предыдущих версий .NET Framework. Если приложение зависит от устаревшего поведения, можно восстановить правила сравнения строк и сортировки, используемые в .NET Framework 3,5 и более ранних версиях, включив элемент `<CompatSortNLSVersion>` в файл конфигурации приложения.  
  
> [!IMPORTANT]
> Для восстановления устаревших правил сравнения и сортировки строк также требуется, чтобы в локальной системе была доступна библиотека динамической компоновки sort00001000.dll.  
  
 Устаревшие правила сортировки и сравнения строк можно также использовать в конкретном домене приложения, передав при создании этого домена строку "NetFx40_Legacy20SortingBehavior" в метод <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере создаются экземпляры двух объектов <xref:System.String> и вызывается метод <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>, чтобы сравнить их с использованием соглашений текущих языка и региональных параметров.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 При запуске примера на .NET Framework 4 отображаются следующие выходные данные.  
  
```  
sta follows a in the sort order.  
```  
  
 Он совершенно отличается от выходных данных, отображаемых при выполнении примера на .NET Framework 3,5.  
  
```  
sta equals a in the sort order.  
```  
  
 Однако если добавить в каталог примера следующий файл конфигурации, а затем запустить пример на .NET Framework 4, то выходные данные идентичны тому, что были созданы в примере при его запуске на .NET Framework 3,5.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)

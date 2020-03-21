---
title: Элемент <UseRandomizedStringHashAlgorithm>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153781"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm> элемент
Определяет, вычисляет ли общее время выполнения языка хэш-коды для строк на основе домена приложения.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Уточняется, рассчитываются ли хэш-коды для строк на основе домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`0`|Общее время выполнения языка не вычисляет хэш-коды для строк на основе домена в приложении; для расчета кодов хэша строк используется один алгоритм. Это значение по умолчанию.|  
|`1`|Общий язык runtime вычисляет коды хэша для строк на основе домена приложения. Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Remarks  
 По умолчанию <xref:System.StringComparer> класс <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> и метод используют единый алгоритм хэширования, который производит согласованный хэш-код в доменах приложений. Это эквивалентно настройке атрибута `enabled` элемента. `<UseRandomizedStringHashAlgorithm>` `0` Это алгоритм хэширования, используемый в системе .NET 4.  
  
 Класс <xref:System.StringComparer> и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод также могут использовать другой алгоритм хэширования, который вычисляет хэш-коды на основе домена приложения. В результате хэш-коды для эквивалентных строк будут отличаться в разных доменах приложений. Это функция выбора; чтобы воспользоваться им, вы `enabled` должны установить `1`атрибут элемента. `<UseRandomizedStringHashAlgorithm>`  
  
 Поиск строки в таблице хэша обычно является операцией O(1). Однако при большом количестве столкновений поиск может стать операцией O(n<sup>2).</sup> Элемент `<UseRandomizedStringHashAlgorithm>` конфигурации можно использовать для генерации алгоритма случайного хэширования в домене приложения, что, в свою очередь, ограничивает количество потенциальных столкновений, особенно когда ключи, из которых рассчитываются хэш-коды, основаны на ввода данных пользователями.  
  
## <a name="example"></a>Пример  
 Следующий пример определяет `DisplayString` класс, который включает `s`в себя константу частной строки, значение которого "Это строка". Он также включает метод `ShowStringHashCode`, который отображает значение строки и ее хэш-код вместе с именем домена приложения, в котором метод выполняется.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 При выполнении примера без указания файла конфигурации он отображает подобный следующему вывод. Обратите внимание, что хэш-коды для строки идентичны в обоих доменах приложений.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Однако при добавлении следующего файла конфигурации в каталог примеров и запуске примера, хэш-коды для той же строки будут отличаться по домену приложения.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Если файл конфигурации существует, пример отображает следующие выходные данные:  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

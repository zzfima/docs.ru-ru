---
title: <UseRandomizedStringHashAlgorithm> Элемент
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a51b9fb485da605effbad0e81b8baf5e05e382a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087798"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm > элемент
Определяет, вычисляет ли среда CLR хэш-коды для строк на основе доменов приложения.  
  
 \<configuration>  
\<Среда выполнения >  
\<UseRandomizedStringHashAlgorithm >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, вычисляются ли хэш-коды для строк на основе доменов приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`0`|Среда CLR не вычисляет хэш-коды для строк для каждого домена приложения; для вычисления хэш-кодов строк используется один алгоритм. Это значение по умолчанию.|  
|`1`|Среда CLR вычисляет хэш-коды для строк на основе доменов приложения. Одинаковых строк в различных доменах приложений и в различных процессах будут иметь разные хэш-коды.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию <xref:System.StringComparer> класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод использования один алгоритм хэширования, который создает последовательный хэш-код между доменами приложений. Это эквивалентно параметр `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `0`. Это алгоритм хэширования, используемый в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 <xref:System.StringComparer> Класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод можно также использовать другой алгоритм хэширования, который вычисляет хэш-коды для каждого домена приложения. В результате хэш-коды для эквивалентных строк будут отличаться в разных доменах приложений. Это функция в; Чтобы воспользоваться его преимуществами, необходимо задать `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `1`.  
  
 Поиск строки в хэш-таблицы обычно является операцией O(1). Тем не менее, если не возникает большое количество конфликтов, поиск может стать операцией O (n<sup>2</sup>) операции. Можно использовать `<UseRandomizedStringHashAlgorithm>` элемент конфигурации, чтобы создать случайный алгоритм хэширования в каждом домене приложения, который в свою очередь ограничивает число потенциальных конфликтов, особенно в том случае, если ключи, из которых вычисляется хэш-кодов, основаны на входных данных пользователями.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `DisplayString` класс, который включает закрытую строковую константу, `s`, значение которого равно «This is a string». Он также включает `ShowStringHashCode` метод, отображающий значение строки и ее хэш-код вместе с именем домена приложения, в котором метод выполняется.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 При выполнении примера без указания файла конфигурации отображается результат, аналогичный приведенному ниже. Обратите внимание на то, что хэш-коды для строки идентичны в обоих доменах приложений.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Тем не менее если добавить следующий файл конфигурации в каталог примеров и запустить пример, хэш-коды для той же строки будут отличаться по домену приложения.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Если присутствует в файле конфигурации, пример отображает следующие выходные данные:  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

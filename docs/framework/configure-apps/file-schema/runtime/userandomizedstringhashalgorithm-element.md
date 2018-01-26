---
title: "&lt;UseRandomizedStringHashAlgorithm&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6231f362a30f4766ccf5a43d33fa0dc7257ad57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a>&lt;UseRandomizedStringHashAlgorithm&gt; элемент
Определяет, вычисляет ли среда хэш-кодов для строк для каждого домена приложения.  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, вычисляются ли хэш-кодов для строк на каждого домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`0`|Общеязыковая среда выполнения не вычисляет хэш-кодов для строк для каждого домена приложения; один алгоритм используется для вычисления хэш-кодов строки. Это значение по умолчанию.|  
|`1`|Общеязыковая среда выполнения вычисляет хэш-кодов для строк для каждого домена приложения. Одинаковых строк в различных доменах приложений и в разных процессах будет иметь другой хэш-кодов.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию <xref:System.StringComparer> класса и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод использования один алгоритм хэширования, который создает согласованные хэш-код в доменах приложений. Это значение эквивалентно значению параметра `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `0`. Это алгоритм хэширования, используемый в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 <xref:System.StringComparer> Класса и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод также можно использовать другой алгоритм хэширования, который вычисляет хэш-коды для каждого домена приложения. В результате хэш-кодов для строк, эквивалентный будут отличаться в доменах приложений. Это функция, включаемая; Чтобы использовать его, необходимо задать `enabled` атрибут `<UseRandomizedStringHashAlgorithm>` элемент `1`.  
  
 Поиск строки в хэш-таблицы, обычно является операцией o(1). Однако при возникновении большое число конфликтов, уточняющего запроса может стать O (n<sup>2</sup>) операции. Можно использовать `<UseRandomizedStringHashAlgorithm>` элемента конфигурации для формирования случайных алгоритма хэширования, домена приложения, в свою очередь ограничивает число потенциальные конфликты, особенно в том случае, если ключи, из которых вычисляется хэш-кодов, основаны на входных данных пользователями.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `DisplayString` класс, который содержит частную строковую константу, `s`, значение которого является «Это строка». Он также включает `ShowStringHashCode` метод, отображающий строковый параметр и его хэш-код, вместе с именем домена приложения, в котором выполняется метод.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 При запуске примера без указания файла конфигурации будет выведен текст следующего вида. Обратите внимание, что хэш-кодов для строки идентичны в двух доменов приложений.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Однако если добавить следующий файл конфигурации в каталога примера и запустить пример, хэш-кодов для строк будут отличаться по доменам приложений.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Если присутствует в файле конфигурации, в примере отображается следующий результат:  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

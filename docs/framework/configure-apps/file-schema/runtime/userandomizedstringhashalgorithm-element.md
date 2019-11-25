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
ms.openlocfilehash: 3863bc1376d89ef804022fb9c87fac3a25fc910f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968835"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm > элемент
Определяет, вычисляет ли среда CLR хэш-коды для строк на уровне домена приложения.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<UseRandomizedStringHashAlgorithm >**  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, рассчитываются ли хэш-коды для строк на уровне домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|значения|Описание|  
|-----------|-----------------|  
|`0`|Среда CLR не выполняет вычисление хэш-кодов для строк на уровне отдельных приложений. для вычисления хэш-кодов строк используется один алгоритм. Это значение по умолчанию.|  
|`1`|Среда CLR выдает хэш-коды для строк на уровне домена приложения. Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Заметки  
 По умолчанию класс <xref:System.StringComparer> и метод <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> используют один алгоритм хэширования, который создает согласованный хэш-код между доменами приложений. Это эквивалентно установке атрибута `enabled` элемента `<UseRandomizedStringHashAlgorithm>` для `0`. Это алгоритм хэширования, используемый в .NET Framework 4.  
  
 Класс <xref:System.StringComparer> и метод <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> также могут использовать другой алгоритм хэширования, который выполняет вычисление хэш-кодов для каждого домена приложения. В результате хэш-коды для эквивалентных строк будут различаться в разных доменах приложений. Эта функция является обязательной. чтобы воспользоваться его преимуществами, необходимо задать атрибуту `enabled` элемента `<UseRandomizedStringHashAlgorithm>` значение `1`.  
  
 Поиск строки в хэш-таблице обычно является операцией O (1). Однако при возникновении большого количества конфликтов Поиск может стать операцией O (n<sup>2</sup>). Можно использовать элемент конфигурации `<UseRandomizedStringHashAlgorithm>`, чтобы создать случайный алгоритм хэширования для каждого домена приложений, который, в свою очередь, ограничивает количество потенциальных конфликтов, особенно когда ключи, из которых вычисляется хэш-коды, основываются на вводе данных. пользователей.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется класс `DisplayString`, содержащий закрытую строковую константу, `s`, значением которой является строка. Он также включает метод `ShowStringHashCode`, который отображает строковое значение и его хэш-код, а также имя домена приложения, в котором выполняется метод.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 При запуске примера без указания файла конфигурации отображаются выходные данные, аналогичные приведенным ниже. Обратите внимание, что хэш-коды строк идентичны в двух доменах приложений.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Однако, если добавить следующий файл конфигурации в каталог примера, а затем запустить пример, хэш-коды для одной и той же строки будут отличаться для домена приложения.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 При наличии файла конфигурации в примере выводятся следующие выходные данные:  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

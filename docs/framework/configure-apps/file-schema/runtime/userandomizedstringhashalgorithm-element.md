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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b53dcd4db7e0ac1e9079e763b8ed76c1088e0e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252203"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<Элемент > UseRandomizedStringHashAlgorithm
Определяет, вычисляет ли среда CLR хэш-коды для строк на уровне домена приложения.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
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
  
|Значение|Описание|  
|-----------|-----------------|  
|`0`|Среда CLR не выполняет вычисление хэш-кодов для строк на уровне отдельных приложений. для вычисления хэш-кодов строк используется один алгоритм. Это значение по умолчанию.|  
|`1`|Среда CLR выдает хэш-коды для строк на уровне домена приложения. Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию <xref:System.StringComparer> класс <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> и метод используют один алгоритм хэширования, который создает согласованный хэш-код между доменами приложений. Это эквивалентно присвоению `enabled` атрибуту `<UseRandomizedStringHashAlgorithm>` элемента `0`значения. Это алгоритм хэширования, используемый в .NET Framework 4.  
  
 <xref:System.StringComparer> Класс<xref:System.String.GetHashCode%2A?displayProperty=nameWithType> и метод могут также использовать другой алгоритм хэширования, который выполняет вычисление хэш-кодов для каждого домена приложения. В результате хэш-коды для эквивалентных строк будут различаться в разных доменах приложений. Эта функция является обязательной. чтобы воспользоваться его преимуществами, необходимо задать `enabled` атрибуту `<UseRandomizedStringHashAlgorithm>` элемента `1`значение.  
  
 Поиск строки в хэш-таблице обычно является операцией O (1). Однако при возникновении большого количества конфликтов Поиск может стать операцией O (n<sup>2</sup>). Элемент `<UseRandomizedStringHashAlgorithm>` Configuration можно использовать для создания алгоритма случайного хэширования на домен приложения, который, в свою очередь, ограничивает количество потенциальных конфликтов, особенно если ключи, из которых рассчитываются хэш-коды, основаны на вводе данных. пользователями.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `DisplayString` класс, включающий закрытую строковую `s`константу, значение которой равно «это строка». Он также включает `ShowStringHashCode` метод, который отображает строковое значение и его хэш-код, а также имя домена приложения, в котором выполняется метод.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 При запуске примера без указания файла конфигурации отображаются выходные данные, аналогичные приведенным ниже. Обратите внимание, что хэш-коды строк идентичны в двух доменах приложений.  
  
```  
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
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

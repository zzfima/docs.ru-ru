---
title: Строковые канонические функции
ms.date: 03/30/2017
ms.assetid: 5e2cbebd-5df3-47c7-b0e2-49a17ab22bfb
ms.openlocfilehash: 9013b8bd8505442666dd0688eaf2586959a61b70
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249091"
---
# <a name="string-canonical-functions"></a>Строковые канонические функции
Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] включает строковые канонические функции.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице приведены строковые канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Функция|Описание|  
|--------------|-----------------|  
|`Concat(string1, string2)`|Возвращает строку, содержащую строку `string2`, добавленную к строке `string1`.<br /><br /> **Аргументы**<br /><br /> `string1`: Строка, к которой `string2` добавляется.<br /><br /> `string2`: Строка, добавляемая к `string1`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`. Если длина строки возвращаемого значения больше максимально допустимой длины, произойдет ошибка.<br /><br /> **Пример**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Contains(string, target)`|Возвращает значение `true`, если `target` содержится в `string`.<br /><br /> **Аргументы**<br /><br /> `string`: Искомая строка.<br /><br /> `target`: Целевая строка, в которой выполняется поиск.<br /><br /> **Возвращаемое значение**<br /><br /> Значение `true`, если подстрока `target` содержится в строке `string`, в противном случае - значение `false`.<br /><br /> **Пример**<br /><br /> `-- The following example returns true.`<br /><br /> `Contains('abc', 'bc')`|  
|`EndsWith(string, target)`|Возвращает значение `true`, если `target` заканчивается на `string`.<br /><br /> **Аргументы**<br /><br /> `string`: Искомая строка.<br /><br /> `target`: Целевая строка, по которой выполняется поиск, `string`в конце.<br /><br /> **Возвращаемое значение**<br /><br /> Значение `True`, если `string` заканчивается на `target`. В противном случае - значение `false`.<br /><br /> **Пример**<br /><br /> `-- The following example returns true.`<br /><br /> `EndsWith('abc', 'bc')` **Примечание:**  Если используется поставщик данных SQL Server, эта функция возвращает `false` значение, если строка хранится в строковом столбце фиксированной длины и `target` является константой. В данном случае производится поиск по всей строке, включая конечные пробелы заполнения в строке. Данную проблему можно обойти, усекая данные в строке с фиксированной длиной, как это показано в следующем примере: `EndsWith(TRIM(string), target)`|  
|`IndexOf(target, string)`|Возвращает позицию `target` внутри `string` или значение 0, если строка не найдена. Возвращает значение 1, указывая на начало `string`. Нумерация позиций начинается со значения 1.<br /><br /> **Аргументы**<br /><br /> `target`: Искомая строка.<br /><br /> `string`: Искомая строка.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Int32`.<br /><br /> **Пример**<br /><br /> `-- The following example returns 4.`<br /><br /> `IndexOf('xyz', 'abcxyz')`|  
|`Left(string, length)`|Возвращает первые символы `length` с левой стороны `string`. Если длина `string` меньше, чем `length`, возвращается вся строка.<br /><br /> **Аргументы**<br /><br /> `string`: ОБЪЕКТ `String`.<br /><br /> `length`: `Int16` ,`Int32`, Или .`Byte` `Int64` Параметр `length` не может иметь значение меньше нуля.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns abc.`<br /><br /> `Left('abcxyz', 3)`|  
|`Length(string)`|Возвращает (`Int32`) длину строки в символах.<br /><br /> **Аргументы**<br /><br /> `string`: ОБЪЕКТ `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Int32`.<br /><br /> **Пример**<br /><br /> `-- The following example returns 6.`<br /><br /> `Legth('abcxyz')`|  
|`LTrim(string)`|Возвращает `string` без начальных пробелов.<br /><br /> **Аргументы**<br /><br /> Объект `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns abc.`<br /><br /> `LTrim('   abc')`|  
|`Replace(string1, string2, string3)`|Возвращает `string1`, где все вхождения `string2` заменены на `string3`.<br /><br /> **Аргументы**<br /><br /> Объект `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Reverse(string)`|Возвращает `string` с обратным порядком символов.<br /><br /> **Аргументы**<br /><br /> Объект `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns dcba.`<br /><br /> `Reverse('abcd')`|  
|`Right(string, length)`|Возвращает последние `length` символы `string`из. Если длина `string` меньше, чем `length`, возвращается вся строка.<br /><br /> **Аргументы**<br /><br /> `string`: ОБЪЕКТ `String`.<br /><br /> `length`: `Int16` ,`Int32`, Или .`Byte` `Int64` Параметр `length` не может иметь значение меньше нуля.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Right('abcxyz', 3)`|  
|`RTrim(string)`|Возвращает `string` без конечных пробелов.<br /><br /> **Аргументы**<br /><br /> Объект `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.|  
|`Substring(string, start, length)`|Возвращает для строки подстроку, начинающуюся на позиции `start` и длиной `length` символов. Значение аргумента start, равное 1, определяет первый символ строки. Нумерация позиций начинается со значения 1.<br /><br /> **Аргументы**<br /><br /> `string`: ОБЪЕКТ `String`.<br /><br /> `start`: `Int16` ,`Int32`И .`Byte` `Int64` Параметр `start` не может иметь значение меньше единицы.<br /><br /> `length`: `Int16` ,`Int32`И .`Byte` `Int64` Параметр `length` не может иметь значение меньше нуля.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Substring('abcxyz', 4, 3)`|  
|`StartsWith(string, target)`|Возвращает значение `true`, если `string` начинается с `target`.<br /><br /> **Аргументы**<br /><br /> `string`: Искомая строка.<br /><br /> `target`: Целевая строка для поиска в начале `string`.<br /><br /> **Возвращаемое значение**<br /><br /> Значение `True`, если `string` начинается с `target`. В противном случае - значение `false`.<br /><br /> **Пример**<br /><br /> `-- The following example returns true.`<br /><br /> `StartsWith('abc', 'ab')`|  
|`ToLower(string)`|Возвращает `string` с прописными буквами, преобразованными в символы нижнего регистра.<br /><br /> **Аргументы**<br /><br /> Объект `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns abc.`<br /><br /> `ToLower('ABC')`|  
|`ToUpper(string)`|Возвращает `string` с символами нижнего регистра, преобразованными в прописные буквы.<br /><br /> **Аргументы**<br /><br /> Объект `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns ABC.`<br /><br /> `ToUpper('abc')`|  
|`Trim(string)`|Возвращает `string` без начальных и конечных пробелов.<br /><br /> **Аргументы**<br /><br /> Объект `String`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `String`.<br /><br /> **Пример**<br /><br /> `-- The following example returns abc.`<br /><br /> `Trim('      abc   ')`|  
  
 Эти функции возвращают `null` при получении на входе `null`.  
  
 Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL. Дополнительные сведения см. в разделе [SqlClient для функций Entity Framework](../sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>См. также

- [Канонические функции](canonical-functions.md)

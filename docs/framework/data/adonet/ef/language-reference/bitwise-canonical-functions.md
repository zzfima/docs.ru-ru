---
title: Битовые канонические функции
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: df3b81a47b8e1202884a5c38f55c7061279b245f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="bitwise-canonical-functions"></a>Битовые канонические функции
Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] включает битовые канонические функции.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице приведены другие битовые функции [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Эти функции возвращают `Null` Если `Null` ввода данных пользователем. Тип возвращаемого значения функций совпадает с типами аргументов. Аргументы должны относиться к одному и тому же типу, если функция принимает более одного аргумента. Для выполнения битовых операций с различными типами необходимо выполнить явное приведение к одному и тому же типу.  
  
|Функция|Описание|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Возвращает результат битового логического умножения `value1` и `value2` того же типа, что имеют `value1` и `value2`.<br /><br /> **Аргументы**<br /><br /> Объект `Byte`, `Int16`, `Int32`, и `Int64`.<br /><br /> **Пример**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Возвращает результат битового отрицания `value`.<br /><br /> **Аргументы**<br /><br /> Объект `Byte`, `Int16`, `Int32`, и `Int64`.<br /><br /> **Пример**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Возвращает результат битового логического сложения `value1` и `value2` того же типа, что имеют `value1` и `value2`.<br /><br /> **Аргументы**<br /><br /> Объект `Byte`, `Int16`, `Int32` и `Int64`.<br /><br /> **Пример**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Возвращает результат битового исключающего логического сложения `value1` и `value2` того же типа, что имеют `value1` и `value2`.<br /><br /> **Аргументы**<br /><br /> Объект `Byte`, `Int16`, `Int32` и `Int64`.<br /><br /> **Пример**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>См. также  
 [Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)

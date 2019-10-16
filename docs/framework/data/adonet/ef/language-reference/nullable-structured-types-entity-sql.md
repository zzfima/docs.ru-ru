---
title: Допускающие значения null структурированные типы (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: b155c672d8c0bef8b01fb26fb49908f094add25a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319478"
---
# <a name="nullable-structured-types-entity-sql"></a>Допускающие значения null структурированные типы (Entity SQL)
Экземпляр `null` структурированного типа - несуществующий экземпляр. Это отличается от существующего экземпляра, все свойства которого имеют значения `null`.  
  
 В этом разделе описаны структурированные типы, допускающие значение NULL, с указанием, какие типы допускают значение NULL и какие последовательности программного кода формируют экземпляры `null` структурированных типов, допускающих значение NULL.  
  
## <a name="kinds-of-nullable-structured-types"></a>Разновидности структурированных типов, допускающих значение NULL  
 Существует три вида типов структуры, допускающих значения NULL:  
  
- Типы строк.  
  
- Сложные типы.  
  
- Типы сущностей.  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a>Шаблоны кода, которые формируют экземпляры NULL структурированных типов  
 В следующем сценарии формируются экземпляры `null`:  
  
- Формирование `null` как структурированного типа:  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- Приведение базового типа к производному типу:  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- Внешнее соединение по условию FALSE:  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --или  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --или  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- Разыменование ссылки на `null`:  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- Получение значения ANYELEMENT из пустой коллекции:  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- Проверка наличия экземпляров `null` структурированных типов:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](entity-sql-overview.md)

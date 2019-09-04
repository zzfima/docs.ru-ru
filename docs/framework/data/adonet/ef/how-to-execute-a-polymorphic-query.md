---
title: Практическое руководство. Выполнение полиморфного запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 49e0a6b44af0729959fabf6278cc6d8ecf37a16b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251513"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Практическое руководство. Выполнение полиморфного запроса

В этом разделе показано, как выполнить преформацию [!INCLUDE[esql](../../../../../includes/esql-md.md)] запроса с помощью оператора [OFTYPE](./language-reference/oftype-entity-sql.md) .

### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере

1. Добавьте [модель School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) в проект и настройте проект для использования Entity Framework. Дополнительные сведения см. в разделе [Практическое руководство. Используйте мастер](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))EDM.

2. На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Измените концептуальную модель так, чтобы она была наследована с одной таблицей на иерархию [, выполнив действия, описанные в руководстве по выполнению. Наследование сопоставления — таблица на иерархию](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Пример

В следующем примере используется оператор OFTYPE для возврата и отображения коллекции только элементов `OnsiteCourses` из коллекции `Courses`.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>См. также

- [Поставщик EntityClient для Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Язык Entity SQL](./language-reference/entity-sql-language.md)

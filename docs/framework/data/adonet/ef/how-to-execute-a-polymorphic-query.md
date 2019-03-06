---
title: Практическое руководство. выполнить полиморфный запрос
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 08ae5722267ef781ed6bee59c7895269f63a75e5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355556"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Практическое руководство. выполнить полиморфный запрос

В этом разделе показано, как выполнить полиморфный [!INCLUDE[esql](../../../../../includes/esql-md.md)] запрос с использованием [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) оператор.

### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере

1. Добавить [модели School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) в проект и настроить проект для использования платформы Entity Framework. Дополнительные сведения см. в разделе [Как Использовать мастер моделей EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

2. На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Измените концептуальную модель для наследования таблица на иерархию, выполнив действия, описанные в [Пошаговое руководство: Сопоставление наследования — одна таблица на иерархию](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Пример

В следующем примере используется оператор OFTYPE для возврата и отображения коллекции только элементов `OnsiteCourses` из коллекции `Courses`.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>См. также

- [Поставщик EntityClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)

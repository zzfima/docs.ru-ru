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
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="277c6-102">Практическое руководство. выполнить полиморфный запрос</span><span class="sxs-lookup"><span data-stu-id="277c6-102">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="277c6-103">В этом разделе показано, как выполнить полиморфный [!INCLUDE[esql](../../../../../includes/esql-md.md)] запрос с использованием [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) оператор.</span><span class="sxs-lookup"><span data-stu-id="277c6-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="277c6-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="277c6-104">To run the code in this example</span></span>

1. <span data-ttu-id="277c6-105">Добавить [модели School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) в проект и настроить проект для использования платформы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="277c6-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="277c6-106">Дополнительные сведения см. в разделе [Как Использовать мастер моделей EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="277c6-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="277c6-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="277c6-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="277c6-108">Измените концептуальную модель для наследования таблица на иерархию, выполнив действия, описанные в [Пошаговое руководство: Сопоставление наследования — одна таблица на иерархию](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="277c6-108">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="277c6-109">Пример</span><span class="sxs-lookup"><span data-stu-id="277c6-109">Example</span></span>

<span data-ttu-id="277c6-110">В следующем примере используется оператор OFTYPE для возврата и отображения коллекции только элементов `OnsiteCourses` из коллекции `Courses`.</span><span class="sxs-lookup"><span data-stu-id="277c6-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="277c6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="277c6-111">See also</span></span>

- [<span data-ttu-id="277c6-112">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="277c6-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="277c6-113">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="277c6-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)

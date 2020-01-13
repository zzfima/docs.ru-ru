---
title: Руководство по программированию на C#. Свойства интерфейса
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: ff892a35f4be6600c00bc0c72c2f789ef6eb4408
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705539"
---
# <a name="interface-properties-c-programming-guide"></a>Свойства интерфейса (Руководство по программированию на C#)

Свойства можно объявлять для [интерфейса](../../language-reference/keywords/interface.md). Ниже показан пример метода доступа к свойству интерфейса:

[!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]

Метод доступа свойства интерфейса не имеет тела. Таким образом, методы доступа нужны, чтобы указать, доступно ли свойство для чтения и записи, только для чтения или только для записи.

## <a name="example"></a>Пример

В этом примере интерфейс `IEmployee` содержит доступное для чтения и записи свойство `Name`, а также свойство `Counter`, предназначенное только для чтения. Класс `Employee` реализует интерфейс `IEmployee` и использует эти два свойства. Программа считывает имя нового сотрудника и текущее число сотрудников, после чего отображает имя сотрудника и его рассчитанный номер.

Вы можете использовать полное имя свойства, которое ссылается на интерфейс, где был объявлен член. Пример:

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

Это называется [явной реализацией интерфейса](../interfaces/explicit-interface-implementation.md). Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых содержат свойство `Name`, потребуется явная реализация члена интерфейса. Это значит, что потребуется следующее объявление свойства:

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

реализует свойство `Name` в интерфейсе `IEmployee`, тогда как следующее объявление:

[!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]

реализует свойство `Name` в интерфейсе `ICitizen`.

[!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a>Пример полученных результатов

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Свойства](./properties.md)
- [Использование свойств](./using-properties.md)
- [Сравнение свойств и индексаторов](../indexers/comparison-between-properties-and-indexers.md)
- [Индексаторы](../indexers/index.md)
- [Интерфейсы](../interfaces/index.md)

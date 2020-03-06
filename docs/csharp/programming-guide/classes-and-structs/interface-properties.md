---
title: Руководство по программированию на C#. Свойства интерфейса
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626624"
---
# <a name="interface-properties-c-programming-guide"></a>Свойства интерфейса (Руководство по программированию на C#)

Свойства можно объявлять для [интерфейса](../../language-reference/keywords/interface.md). Следующий пример объявляет метод доступа к свойству интерфейса:

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

Свойства интерфейса обычно не имеют тела. Методы доступа указывают, доступно ли свойство для чтения и записи, только для чтения или только для записи. В отличие от классов и структур, объявление методов доступа без тела не приводит к объявлению [автоматически реализуемого свойства](auto-implemented-properties.md). Начиная с C# 8.0 интерфейс может определять реализацию по умолчанию для членов, включая свойства. Определение реализации по умолчанию для свойства в интерфейсе используется редко, так как интерфейсы могут не определять поля данных экземпляра.

## <a name="example"></a>Пример

В этом примере интерфейс `IEmployee` содержит доступное для чтения и записи свойство `Name`, а также свойство `Counter`, предназначенное только для чтения. Класс `Employee` реализует интерфейс `IEmployee` и использует эти два свойства. Программа считывает имя нового сотрудника и текущее число сотрудников, после чего отображает имя сотрудника и его рассчитанный номер.

Вы можете использовать полное имя свойства, которое ссылается на интерфейс, где был объявлен член. Пример:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

В предыдущем примере показана [явная реализация интерфейса](../interfaces/explicit-interface-implementation.md). Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых содержат свойство `Name`, потребуется явная реализация члена интерфейса. Это значит, что потребуется следующее объявление свойства:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

реализует свойство `Name` в интерфейсе `IEmployee`, тогда как следующее объявление:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

реализует свойство `Name` в интерфейсе `ICitizen`.

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

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

---
title: Руководство по программированию на C#. Конструкторы экземпляров
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: ee3cc30334154ef8aae6d7d26286463c537ff3dd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714803"
---
# <a name="instance-constructors-c-programming-guide"></a>Конструкторы экземпляров (Руководство по программированию в C#)

Конструкторы экземпляров используются для создания и инициализации переменных члена экземпляра, если создание объекта [class](../../language-reference/keywords/class.md) осуществляется с помощью выражения [new](../../language-reference/operators/new-operator.md). Для инициализации класса [static](../../language-reference/keywords/static.md) или статических переменных в нестатическом классе определяется статический конструктор. Дополнительные сведения см. в разделе [Статические конструкторы](./static-constructors.md).  
  
 В следующем примере показан конструктор экземпляра.  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> Для ясности этот класс содержит открытые поля. Открытые поля не рекомендуется использовать на практике, поскольку в этом случае любой метод в любом месте программы получает неограниченный и неконтролируемый доступ к внутренней работе объекта. Члены данных обычно должны быть закрытыми, а доступ к ним должен осуществляться только посредством методов и свойства класса.  
  
 Этот конструктор экземпляра вызывается каждый раз при создании объекта на базе класса `Coords`. Такой конструктор без аргументов называется *конструктором без параметров*. Зачастую такие конструкторы используются для предоставления дополнительных конструкторов. Например, можно добавить конструктор в класс `Coords`, позволяющий указывать начальные значения для членов данных:  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 Это позволяет создавать объекты `Coords` с начальными значениями по умолчанию или с другими начальными значениями:  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 Если класс не имеет конструктора, автоматически создается конструктор без параметров и для инициализации полей объекта используются значения по умолчанию. Например, [int](../../language-reference/builtin-types/integral-numeric-types.md) инициализируется значением 0. Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../language-reference/keywords/default-values-table.md). Следовательно, поскольку конструктор без параметров класса `Coords` инициализирует все члены данных с нулевыми значениями, его можно удалить. При этом работа класса не изменится. Полный пример использования нескольких конструкторов см. в данном разделе в примере 1; пример автоматически созданного конструктора см. в примере 2.  
  
 Конструкторы экземпляров также можно использовать для вызова конструкторов экземпляров базового класса. Конструктор класса может вызвать конструктор базового класса с помощью инициализатора:  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 В этом примере класс `Circle` передает значения радиуса и высоты конструктору, предоставленному классом `Shape`, для которого класс `Circle` является производным. Полный текст кода с использованием классов `Shape` и `Circle` см. в данном разделе в примере 3.  
  
## <a name="example-1"></a>Пример 1  
 В следующем примере демонстрируется класс с двумя конструкторами, один из которых не имеет аргументов, а второй имеет два аргумента.  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a>Пример 2  
 В этом примере класс `Person` не имеет конструкторов, поэтому автоматически предоставляется конструктор без параметров, а все поля инициализируются значениями по умолчанию.  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 Обратите внимание, что значение по умолчанию `age` равно `0`, а значение по умолчанию `name` равно `null`. Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../language-reference/keywords/default-values-table.md).  
  
## <a name="example-3"></a>Пример 3  
 В следующем примере демонстрируется использование инициализатора базового класса. Класс `Circle` является производным от основного класса `Shape`, а класс `Cylinder` является производным от класса `Circle`. Конструктор каждого производного класса использует инициализатор своего базового класса.  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 Дополнительные примеры вызова конструкторов базовых классов см. в разделах [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) и [base](../../language-reference/keywords/base.md).  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Конструкторы](./constructors.md)
- [Методы завершения](./destructors.md)
- [static](../../language-reference/keywords/static.md)

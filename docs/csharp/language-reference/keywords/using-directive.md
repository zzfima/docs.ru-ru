---
title: Справочник по C#. Директива using
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 4f7ddad8c3dc12391ef6bf345a73ebb384400b38
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093153"
---
# <a name="using-directive-c-reference"></a>Директива using (справочник по C#)

Директива `using` используется в следующих трех целях.

- Для разрешения использования типов в пространстве имен, чтобы не нужно было квалифицировать использование типа в этом пространстве имен:

    ```csharp
    using System.Text;
    ```

- Для разрешения доступа к статическим членам и вложенным типам без необходимости квалифицировать доступ с помощью имени типа.

    ```csharp
    using static System.Math;
    ```

    Дополнительные сведения см. в разделе [Директива using static](using-static.md).

- Чтобы создать псевдоним для пространства имен или типа. Это называется *директивой using static*.

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

Ключевое слово `using` также используется для создания *операторов using*, которые помогают обеспечить правильную обработку объектов <xref:System.IDisposable>, таких как файлы и шрифты. Дополнительные сведения см. в разделе [Оператор using](using-statement.md).

## <a name="using-static-type"></a>Использование статического типа

Вы можете обращаться к статическим членам типа без необходимости квалификации доступа с помощью имени типа:

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a>Примечания

Область директивы `using` ограничена файлом, в котором она находится.

Директива `using` может отображаться:

- В начале файла исходного кода перед определением пространств имен и типов.
- В пространстве имен перед любыми пространствами имен и типами, объявленными в этом пространстве имен.

В противном случае возникнет ошибка компилятора [CS1529](../../misc/cs1529.md).

Создайте директиву псевдонима `using`, чтобы упростить квалификацию идентификатора для пространства имен или типа. Во всех директивах `using` следует использовать полное пространство имен или тип независимо от того, какие директивы `using` находятся перед ней. В объявлении директивы `using` не может использоваться псевдоним `using`. Например, следующий код вызовет ошибку компиляции:

```csharp
using s = System.Text;
using s.RegularExpressions; // Generates a compiler error.
```

Создайте директиву `using`, чтобы использовать типы в пространстве имен без необходимости указания этого пространства имен. Директива `using` не предоставляет доступ к пространствам имен, вложенным в указанное пространство имен.

Пространства имен делятся на две категории: пользовательские и системные. Пользовательские пространства имен задаются в вашем коде. Список системных пространств имен см. в разделе [Браузер API .NET](../../../../api/index.md).

## <a name="example-1"></a>Пример 1

В следующем примере показано, как задать и использовать псевдоним `using` для пространства имен.

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

Псевдоним using не может иметь открытый универсальный тип с правой стороны. Например, нельзя создать псевдоним using для `List<T>`, но можно создать его для `List<int>`.

## <a name="example-2"></a>Пример 2

В следующем примере показано, как задать директиву `using` и псевдоним `using` для класса.

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Директивы using](~/_csharplang/spec/namespaces.md#using-directives) в статье [Спецификация языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Использование пространств имен](../../programming-guide/namespaces/using-namespaces.md)
- [Ключевые слова в C#](index.md)
- [Пространства имен](../../programming-guide/namespaces/index.md)
- [Оператор using](using-statement.md)

---
title: Ключевое слово namespace. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b5c6b8081c188d5b184930222d54ad8f4b5d7a71
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242767"
---
# <a name="namespace-c-reference"></a>namespace (Справочник по C#)

Ключевое слово `namespace` используется для объявления области действия, которая содержит набор связанных объектов. Пространство имен можно использовать для организации элементов кода и для создания глобально уникальных типов.

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a>Примечания

В пространстве имен можно объявить ноль или больше следующих типов:

- другое пространство имен

- [class](class.md)

- [interface](interface.md)

- [struct](struct.md)

- [enum](enum.md)

- [delegate](delegate.md)

Независимо от того, было ли пространство имен объявлено явным образом в исходном файле на языке C#, компилятор добавляет пространство имен по умолчанию. Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле. Любой идентификатор в глобальном пространстве имен доступен для использования в именованном пространстве имен.

Пространства имен неявно имеют общий доступ, и это невозможно изменить. Описание модификаторов доступа, которые можно назначить элементам в пространстве имен, см. в разделе [Модификаторы доступа](access-modifiers.md).

Пространство имен можно определить в двух или нескольких объявлениях. Например, в следующем примере два класса определяются в качестве части пространства имен `MyCompany`:

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a>Пример

В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a>Связанные ресурсы

Дополнительные сведения об использовании пространств имен см. в следующих разделах:

- [Пространства имен](../../programming-guide/namespaces/index.md)

- [Использование пространств имен](../../programming-guide/namespaces/using-namespaces.md)

- [Практическое руководство. Использование псевдонима глобального пространства имен](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../language-reference/index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Ключевые слова, используемые для пространств имен](namespace-keywords.md)
- [using](using.md)
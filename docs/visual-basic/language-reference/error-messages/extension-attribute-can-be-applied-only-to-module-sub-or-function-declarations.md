---
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 2ed3a10cdf941bb8d1d7c00379736e04e8cad4d7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583185"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="eb694-102">Атрибут Extension может быть применен только к объявлениям Module, Sub или Function</span><span class="sxs-lookup"><span data-stu-id="eb694-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>

<span data-ttu-id="eb694-103">Единственным способом расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля.</span><span class="sxs-lookup"><span data-stu-id="eb694-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="eb694-104">Метод расширения может быть `Sub` процедурой или `Function`ой процедурой.</span><span class="sxs-lookup"><span data-stu-id="eb694-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="eb694-105">Все методы расширения должны быть помечены атрибутом расширения `<Extension()>` из пространства имен <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb694-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="eb694-106">При необходимости модуль, содержащий метод расширения, может быть помечен таким же образом.</span><span class="sxs-lookup"><span data-stu-id="eb694-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="eb694-107">Использование атрибута расширения другим образом не допускается.</span><span class="sxs-lookup"><span data-stu-id="eb694-107">No other use of the extension attribute is valid.</span></span>

<span data-ttu-id="eb694-108">**Идентификатор ошибки:** BC36550</span><span class="sxs-lookup"><span data-stu-id="eb694-108">**Error ID:** BC36550</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="eb694-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="eb694-109">To correct this error</span></span>

- <span data-ttu-id="eb694-110">Удалите атрибут расширения.</span><span class="sxs-lookup"><span data-stu-id="eb694-110">Remove the extension attribute.</span></span>

- <span data-ttu-id="eb694-111">Перепроектирование расширения как метода, определенного во внешнем модуле.</span><span class="sxs-lookup"><span data-stu-id="eb694-111">Redesign your extension as a method, defined in an enclosing module.</span></span>

## <a name="example"></a><span data-ttu-id="eb694-112">Пример</span><span class="sxs-lookup"><span data-stu-id="eb694-112">Example</span></span>

<span data-ttu-id="eb694-113">В следующем примере определяется метод `Print` для `String`ного типа данных.</span><span class="sxs-lookup"><span data-stu-id="eb694-113">The following example defines a `Print` method for the `String` data type.</span></span>

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a><span data-ttu-id="eb694-114">См. также</span><span class="sxs-lookup"><span data-stu-id="eb694-114">See also</span></span>

- [<span data-ttu-id="eb694-115">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="eb694-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="eb694-116">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="eb694-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="eb694-117">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="eb694-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

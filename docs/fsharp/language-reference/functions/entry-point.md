---
title: Точка входа
description: Узнайте, как установить точку входа F# программы, который компилируется как исполняемого файла, где формально начинается выполнение.
ms.date: 05/16/2016
ms.openlocfilehash: c7aedda5834fb224507bfcecd4688978efa26547
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645454"
---
# <a name="entry-point"></a><span data-ttu-id="43f95-103">Точка входа</span><span class="sxs-lookup"><span data-stu-id="43f95-103">Entry Point</span></span>

<span data-ttu-id="43f95-104">В этом разделе описывается метод, который используется для задания точки входа F# программы.</span><span class="sxs-lookup"><span data-stu-id="43f95-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="43f95-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43f95-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="43f95-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="43f95-106">Remarks</span></span>

<span data-ttu-id="43f95-107">В приведенном выше синтаксисе *привязку функция let* является определением функции в `let` привязки.</span><span class="sxs-lookup"><span data-stu-id="43f95-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="43f95-108">Точка входа в программу, которая компилируется как исполняемый файл является формально начала выполнения.</span><span class="sxs-lookup"><span data-stu-id="43f95-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="43f95-109">Укажите точку входа для F# приложения путем применения `EntryPoint` атрибут в программу `main` функции.</span><span class="sxs-lookup"><span data-stu-id="43f95-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="43f95-110">Эта функция (созданные с помощью `let` привязки) должна быть последней функцией в последнем скомпилированном файле.</span><span class="sxs-lookup"><span data-stu-id="43f95-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="43f95-111">Последний скомпилированного файла является последний файл проекта или последнего файла, который передается в командную строку.</span><span class="sxs-lookup"><span data-stu-id="43f95-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="43f95-112">Функция точки входа имеет тип `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="43f95-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="43f95-113">Аргументы, предоставленные в командной строке передаются `main` функции в массив строк.</span><span class="sxs-lookup"><span data-stu-id="43f95-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="43f95-114">Первый элемент массива является первым аргументом; Имя исполняемого файла не включается в массиве, как в некоторых других языков.</span><span class="sxs-lookup"><span data-stu-id="43f95-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="43f95-115">Возвращаемое значение используется как код выхода для процесса.</span><span class="sxs-lookup"><span data-stu-id="43f95-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="43f95-116">Ноль обычно указывает на успешное завершение; ненулевые значения указывают на ошибку.</span><span class="sxs-lookup"><span data-stu-id="43f95-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="43f95-117">Имеют каких-либо конкретных значений ненулевое коды возврата. значения кодов возврата относятся к конкретным приложениям.</span><span class="sxs-lookup"><span data-stu-id="43f95-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="43f95-118">В следующем примере показан простой `main` функции.</span><span class="sxs-lookup"><span data-stu-id="43f95-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="43f95-119">При выполнении этого кода с помощью командной строки `EntryPoint.exe 1 2 3`, результат выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="43f95-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="43f95-120">Неявная точка входа</span><span class="sxs-lookup"><span data-stu-id="43f95-120">Implicit Entry Point</span></span>

<span data-ttu-id="43f95-121">Если в программе нет **EntryPoint** атрибут, который явно указывает точку входа, привязки верхнего уровня в последнем файле компилируемом используются в качестве точки входа.</span><span class="sxs-lookup"><span data-stu-id="43f95-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="43f95-122">См. также</span><span class="sxs-lookup"><span data-stu-id="43f95-122">See also</span></span>

- [<span data-ttu-id="43f95-123">Функции</span><span class="sxs-lookup"><span data-stu-id="43f95-123">Functions</span></span>](index.md)
- [<span data-ttu-id="43f95-124">Привязки let</span><span class="sxs-lookup"><span data-stu-id="43f95-124">let Bindings</span></span>](let-bindings.md)

---
title: "Точка входа (F#)"
description: "Узнайте, как задать точку входа для программы на F #, скомпилированный в качестве исполняемого файла, где формально начинается выполнение."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 91455443-ff9d-4510-a7e9-1560bdcd0bb0
ms.openlocfilehash: 685fd4da67119aa5fcaaffd142a0a17c8f5dc7f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="entry-point"></a><span data-ttu-id="15174-104">Точка входа</span><span class="sxs-lookup"><span data-stu-id="15174-104">Entry Point</span></span>

<span data-ttu-id="15174-105">В этом разделе описывается метод, который позволяет установить точку входа для программы на F #.</span><span class="sxs-lookup"><span data-stu-id="15174-105">This topic describes the method that you use to set the entry point to an F# program.</span></span>


## <a name="syntax"></a><span data-ttu-id="15174-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15174-106">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="15174-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="15174-107">Remarks</span></span>
<span data-ttu-id="15174-108">В предыдущем синтаксисе *привязку let функция* является определением функции в `let` привязки.</span><span class="sxs-lookup"><span data-stu-id="15174-108">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="15174-109">Точка входа для программы, которая компилируется как исполняемый файл является формально начала выполнения.</span><span class="sxs-lookup"><span data-stu-id="15174-109">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="15174-110">Точка входа для приложения на F # задается путем применения `EntryPoint` атрибута в программу `main` функции.</span><span class="sxs-lookup"><span data-stu-id="15174-110">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="15174-111">Эта функция (созданные с помощью `let` привязки) должна быть последней функцией в последнем скомпилированном файле.</span><span class="sxs-lookup"><span data-stu-id="15174-111">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="15174-112">Последний скомпилированном файле является последний файл проекта или последний файл, который передается в командную строку.</span><span class="sxs-lookup"><span data-stu-id="15174-112">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="15174-113">Функция точки входа имеет тип `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="15174-113">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="15174-114">Аргументы, предоставленные в командной строке передаются `main` функции в массив строк.</span><span class="sxs-lookup"><span data-stu-id="15174-114">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="15174-115">Первый элемент массива является первым аргументом; Имя исполняемого файла не включается в массиве, как в некоторых других языков.</span><span class="sxs-lookup"><span data-stu-id="15174-115">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="15174-116">Возвращаемое значение используется как код выхода для процесса.</span><span class="sxs-lookup"><span data-stu-id="15174-116">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="15174-117">Ноль обычно означает успешное завершение; ненулевое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="15174-117">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="15174-118">Нет соглашения конкретных значений ненулевое значение, коды возврата. значения кодов возврата зависят от приложения.</span><span class="sxs-lookup"><span data-stu-id="15174-118">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="15174-119">В следующем примере показан простой `main` функции.</span><span class="sxs-lookup"><span data-stu-id="15174-119">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="15174-120">После выполнения кода с помощью командной строки `EntryPoint.exe 1 2 3`, выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="15174-120">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="15174-121">Неявная точка входа</span><span class="sxs-lookup"><span data-stu-id="15174-121">Implicit Entry Point</span></span>
<span data-ttu-id="15174-122">Если в программе нет **EntryPoint** атрибут, который явным образом указывает точку входа, скомпилировать привязки высшего уровня в последнем файле используются в качестве точки входа.</span><span class="sxs-lookup"><span data-stu-id="15174-122">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>


## <a name="see-also"></a><span data-ttu-id="15174-123">См. также</span><span class="sxs-lookup"><span data-stu-id="15174-123">See Also</span></span>
[<span data-ttu-id="15174-124">Функции</span><span class="sxs-lookup"><span data-stu-id="15174-124">Functions</span></span>](index.md)

[<span data-ttu-id="15174-125">Привязки let</span><span class="sxs-lookup"><span data-stu-id="15174-125">let Bindings</span></span>](let-bindings.md)

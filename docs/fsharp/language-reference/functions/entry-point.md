---
title: Точка входа
description: Узнайте, как задать точку входа для F# программы, которая компилируется как исполняемый файл, где выполнение формально начинается.
ms.date: 05/16/2016
ms.openlocfilehash: 5e13416131d4dfd22583439fedf51f18f7a461da
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630521"
---
# <a name="entry-point"></a><span data-ttu-id="948fe-103">Точка входа</span><span class="sxs-lookup"><span data-stu-id="948fe-103">Entry Point</span></span>

<span data-ttu-id="948fe-104">В этом разделе описывается метод, используемый для задания точки входа в F# программу.</span><span class="sxs-lookup"><span data-stu-id="948fe-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="948fe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="948fe-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="948fe-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="948fe-106">Remarks</span></span>

<span data-ttu-id="948fe-107">В предыдущем синтаксисе *let-Function-Binding* является определением функции в `let` привязке.</span><span class="sxs-lookup"><span data-stu-id="948fe-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="948fe-108">Точкой входа для программы, компилируемой как исполняемый файл, является место, где выполнение формально начинается.</span><span class="sxs-lookup"><span data-stu-id="948fe-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="948fe-109">Вы указываете точку входа для F# приложения, применяя `EntryPoint` атрибут `main` к функции программы.</span><span class="sxs-lookup"><span data-stu-id="948fe-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="948fe-110">Эта функция (созданная с помощью `let` привязки) должна быть последней функцией в последнем скомпилированном файле.</span><span class="sxs-lookup"><span data-stu-id="948fe-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="948fe-111">Последний скомпилированный файл — это последний файл в проекте или последний файл, который передается в командную строку.</span><span class="sxs-lookup"><span data-stu-id="948fe-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="948fe-112">Функция точки входа имеет тип `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="948fe-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="948fe-113">Аргументы, указанные в командной строке, передаются `main` в функцию в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="948fe-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="948fe-114">Первый элемент массива является первым аргументом; Имя исполняемого файла не включается в массив, так как оно находится на других языках.</span><span class="sxs-lookup"><span data-stu-id="948fe-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="948fe-115">Возвращаемое значение используется в качестве кода выхода для процесса.</span><span class="sxs-lookup"><span data-stu-id="948fe-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="948fe-116">Ноль обычно указывает на успешное выполнение; ненулевые значения указывают на ошибку.</span><span class="sxs-lookup"><span data-stu-id="948fe-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="948fe-117">Не существует соглашения для конкретного значения ненулевых кодов возврата; значения кодов возврата зависят от конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="948fe-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="948fe-118">В следующем примере показана простая `main` функция.</span><span class="sxs-lookup"><span data-stu-id="948fe-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="948fe-119">При выполнении этого кода с помощью командной строки `EntryPoint.exe 1 2 3`выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="948fe-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="948fe-120">Неявная точка входа</span><span class="sxs-lookup"><span data-stu-id="948fe-120">Implicit Entry Point</span></span>

<span data-ttu-id="948fe-121">Если у программы нет атрибута **EntryPoint** , который явно указывает на точку входа, то в качестве точки входа используются привязки верхнего уровня в последнем компилируемом файле.</span><span class="sxs-lookup"><span data-stu-id="948fe-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="948fe-122">См. также</span><span class="sxs-lookup"><span data-stu-id="948fe-122">See also</span></span>

- [<span data-ttu-id="948fe-123">Функции</span><span class="sxs-lookup"><span data-stu-id="948fe-123">Functions</span></span>](index.md)
- [<span data-ttu-id="948fe-124">Привязки let</span><span class="sxs-lookup"><span data-stu-id="948fe-124">let Bindings</span></span>](let-bindings.md)

---
title: "Копирование и обновление записей выражения (F #)"
description: "Дополнительные сведения о записи указанного поля «копирование и обновление записей выражение» копирует существующие записи, обновления, а также возвращает обновленной записи."
keywords: "visual f#, f#, функциональное программирование"
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b5fc4ef0-64eb-4272-96a7-bb4dffbb634a
ms.openlocfilehash: 2eb51842b678780a1d6da96e237ebb92d1ea5cec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="f5433-104">Копирование и обновление выражений записей</span><span class="sxs-lookup"><span data-stu-id="f5433-104">Copy and Update Record Expressions</span></span>

<span data-ttu-id="f5433-105">Объект *копирование и обновление записей выражение* выражение, которое копирует существующую запись, затем обновляет указанные поля и возвращает обновленной записи.</span><span class="sxs-lookup"><span data-stu-id="f5433-105">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="f5433-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5433-106">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="f5433-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5433-107">Remarks</span></span>
<span data-ttu-id="f5433-108">Записи являются неизменяемыми, по умолчанию, таким образом, что нет обновления для существующей записи невозможно.</span><span class="sxs-lookup"><span data-stu-id="f5433-108">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="f5433-109">Для создания обновленной записи все поля записи бы быть определен повторно.</span><span class="sxs-lookup"><span data-stu-id="f5433-109">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="f5433-110">Чтобы упростить процесс *копирование и обновление записей выражение* может использоваться.</span><span class="sxs-lookup"><span data-stu-id="f5433-110">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="f5433-111">Это выражение принимает существующей записи, создает новый того же типа, используя указанные поля из выражения и отсутствует поле, указанное выражение.</span><span class="sxs-lookup"><span data-stu-id="f5433-111">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="f5433-112">Это полезно в том случае, если необходимо скопировать существующую запись и при необходимости измените значения полей.</span><span class="sxs-lookup"><span data-stu-id="f5433-112">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="f5433-113">Созданная запись занять для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f5433-113">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="f5433-114">Если нужно обновить только на поля этой записи, можно использовать *копирование и обновление записей выражение* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5433-114">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="f5433-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f5433-115">See Also</span></span>
[<span data-ttu-id="f5433-116">Записи</span><span class="sxs-lookup"><span data-stu-id="f5433-116">Records</span></span>](records.md)

[<span data-ttu-id="f5433-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f5433-117">F# Language Reference</span></span>](index.md)

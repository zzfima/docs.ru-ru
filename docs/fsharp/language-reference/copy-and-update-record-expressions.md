---
title: Копирование и обновление выражений записей
description: Вы можете научиться писать «копировать и обновить выражение», копирует существующую запись или записи в анонимные и обновления поля и возвращает обновленной записи или анонимные записи.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: d16f5ca337047ab2eecc8828b21d8a423bf39a1f
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041739"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="c6dd7-103">Копирование и обновление выражений записей</span><span class="sxs-lookup"><span data-stu-id="c6dd7-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="c6dd7-104">Объект *копирование и обновление выражений записей* выражение, которое копирует существующую запись, затем обновляет указанные поля и возвращает обновленной записи.</span><span class="sxs-lookup"><span data-stu-id="c6dd7-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6dd7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6dd7-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="c6dd7-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6dd7-106">Remarks</span></span>

<span data-ttu-id="c6dd7-107">Записи и анонимный записи являются неизменяемыми по умолчанию, таким образом, возможна по существующей записи не обновляются.</span><span class="sxs-lookup"><span data-stu-id="c6dd7-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="c6dd7-108">Для создания обновленной записи все поля записи придется задать снова.</span><span class="sxs-lookup"><span data-stu-id="c6dd7-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="c6dd7-109">Для упрощения этой задачи *копирование и обновление выражений* может использоваться.</span><span class="sxs-lookup"><span data-stu-id="c6dd7-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="c6dd7-110">Это выражение принимает существующую запись, создает новый того же типа, используя указанные поля из выражения и отсутствует поле, указанных с помощью выражения.</span><span class="sxs-lookup"><span data-stu-id="c6dd7-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="c6dd7-111">Это может быть полезно, если необходимо скопировать существующую запись и при необходимости измените некоторые значения поля.</span><span class="sxs-lookup"><span data-stu-id="c6dd7-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="c6dd7-112">Возьмем например созданной записи.</span><span class="sxs-lookup"><span data-stu-id="c6dd7-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="c6dd7-113">Если пришлось обновлять только в поле этой записи можно использовать *копирование и обновление выражений записей* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c6dd7-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="c6dd7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c6dd7-114">See also</span></span>

- [<span data-ttu-id="c6dd7-115">Записи</span><span class="sxs-lookup"><span data-stu-id="c6dd7-115">Records</span></span>](records.md)
- [<span data-ttu-id="c6dd7-116">Анонимные записей</span><span class="sxs-lookup"><span data-stu-id="c6dd7-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="c6dd7-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="c6dd7-117">F# Language Reference</span></span>](index.md)

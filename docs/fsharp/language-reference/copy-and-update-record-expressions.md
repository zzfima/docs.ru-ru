---
title: Копирование и обновление выражений записей
description: Узнайте, как создать выражение копирования и обновления, которое копирует существующую запись или анонимную запись, обновляет указанные поля и возвращает обновленную запись или анонимную запись.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630377"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="6aaa2-103">Копирование и обновление выражений записей</span><span class="sxs-lookup"><span data-stu-id="6aaa2-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="6aaa2-104">*Выражение записи копирования и обновления* — это выражение, которое копирует существующую запись, обновляет указанные поля и возвращает обновленную запись.</span><span class="sxs-lookup"><span data-stu-id="6aaa2-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="6aaa2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6aaa2-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="6aaa2-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="6aaa2-106">Remarks</span></span>

<span data-ttu-id="6aaa2-107">Записи и анонимные записи являются неизменяемыми по умолчанию, поэтому обновление существующей записи невозможно.</span><span class="sxs-lookup"><span data-stu-id="6aaa2-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="6aaa2-108">Чтобы создать обновленную запись, необходимо снова указать все поля записи.</span><span class="sxs-lookup"><span data-stu-id="6aaa2-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="6aaa2-109">Чтобы упростить эту задачу, можно использовать *выражение копирования и обновления* .</span><span class="sxs-lookup"><span data-stu-id="6aaa2-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="6aaa2-110">Это выражение принимает существующую запись, создает новый объект того же типа, используя указанные поля из выражения и отсутствующее поле, указанное выражением.</span><span class="sxs-lookup"><span data-stu-id="6aaa2-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="6aaa2-111">Это может быть полезно, если необходимо скопировать существующую запись и, возможно, изменить некоторые значения полей.</span><span class="sxs-lookup"><span data-stu-id="6aaa2-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="6aaa2-112">Возьмем для экземпляра созданную запись.</span><span class="sxs-lookup"><span data-stu-id="6aaa2-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="6aaa2-113">Если необходимо обновить только поле в этой записи, можно использовать *выражение копирования и обновления записей* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6aaa2-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="6aaa2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6aaa2-114">See also</span></span>

- [<span data-ttu-id="6aaa2-115">Записи</span><span class="sxs-lookup"><span data-stu-id="6aaa2-115">Records</span></span>](records.md)
- [<span data-ttu-id="6aaa2-116">Анонимные записи</span><span class="sxs-lookup"><span data-stu-id="6aaa2-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="6aaa2-117">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="6aaa2-117">F# Language Reference</span></span>](index.md)

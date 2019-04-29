---
title: Копирование и обновление выражений записей
description: Вы можете научиться писать «копировать и обновить записи выражение» копирует существующих записей, обновления полей и возвращает обновленной записи.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 5f9b13ebf6c456aff73872b7522d7670c068dd88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766055"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="3da68-103">Копирование и обновление выражений записей</span><span class="sxs-lookup"><span data-stu-id="3da68-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="3da68-104">Объект *копирование и обновление выражений записей* выражение, которое копирует существующую запись, затем обновляет указанные поля и возвращает обновленной записи.</span><span class="sxs-lookup"><span data-stu-id="3da68-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="3da68-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3da68-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="3da68-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="3da68-106">Remarks</span></span>

<span data-ttu-id="3da68-107">Записи являются неизменяемыми по умолчанию, таким образом, возможна по существующей записи не обновляются.</span><span class="sxs-lookup"><span data-stu-id="3da68-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="3da68-108">Для создания обновленной записи все поля записи придется задать снова.</span><span class="sxs-lookup"><span data-stu-id="3da68-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="3da68-109">Для упрощения этой задачи *копирование и обновление выражений записей* может использоваться.</span><span class="sxs-lookup"><span data-stu-id="3da68-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="3da68-110">Это выражение принимает существующую запись, создает новый того же типа, используя указанные поля из выражения и отсутствует поле, указанных с помощью выражения.</span><span class="sxs-lookup"><span data-stu-id="3da68-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="3da68-111">Это может быть полезно, если необходимо скопировать существующую запись и при необходимости измените некоторые значения поля.</span><span class="sxs-lookup"><span data-stu-id="3da68-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="3da68-112">Возьмем например созданной записи.</span><span class="sxs-lookup"><span data-stu-id="3da68-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="3da68-113">Если пришлось обновлять только в поле этой записи можно использовать *копирование и обновление выражений записей* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3da68-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="3da68-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3da68-114">See also</span></span>

- [<span data-ttu-id="3da68-115">Записи</span><span class="sxs-lookup"><span data-stu-id="3da68-115">Records</span></span>](records.md)
- [<span data-ttu-id="3da68-116">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="3da68-116">F# Language Reference</span></span>](index.md)
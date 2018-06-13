---
title: 'Копирование и обновление записей выражения (F #)'
description: Дополнительные сведения о записи указанного поля «копирование и обновление записей выражение» копирует существующие записи, обновления, а также возвращает обновленной записи.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 000746b6e76349ae6d8f338519a58034f4e29020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563063"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="22291-103">Копирование и обновление выражений записей</span><span class="sxs-lookup"><span data-stu-id="22291-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="22291-104">Объект *копирование и обновление записей выражение* выражение, которое копирует существующую запись, затем обновляет указанные поля и возвращает обновленной записи.</span><span class="sxs-lookup"><span data-stu-id="22291-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="22291-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22291-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="22291-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="22291-106">Remarks</span></span>
<span data-ttu-id="22291-107">Записи являются неизменяемыми, по умолчанию, таким образом, что нет обновления для существующей записи невозможно.</span><span class="sxs-lookup"><span data-stu-id="22291-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="22291-108">Для создания обновленной записи все поля записи бы быть определен повторно.</span><span class="sxs-lookup"><span data-stu-id="22291-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="22291-109">Чтобы упростить процесс *копирование и обновление записей выражение* может использоваться.</span><span class="sxs-lookup"><span data-stu-id="22291-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="22291-110">Это выражение принимает существующей записи, создает новый того же типа, используя указанные поля из выражения и отсутствует поле, указанное выражение.</span><span class="sxs-lookup"><span data-stu-id="22291-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="22291-111">Это полезно в том случае, если необходимо скопировать существующую запись и при необходимости измените значения полей.</span><span class="sxs-lookup"><span data-stu-id="22291-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="22291-112">Созданная запись занять для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="22291-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="22291-113">Если нужно обновить только на поля этой записи, можно использовать *копирование и обновление записей выражение* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="22291-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="22291-114">См. также</span><span class="sxs-lookup"><span data-stu-id="22291-114">See Also</span></span>
[<span data-ttu-id="22291-115">Записи</span><span class="sxs-lookup"><span data-stu-id="22291-115">Records</span></span>](records.md)

[<span data-ttu-id="22291-116">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="22291-116">F# Language Reference</span></span>](index.md)

---
title: 'Копирование и обновление выражений записей (F #)'
description: Вы можете научиться писать «копировать и обновить записи выражение» копирует существующих записей, обновления полей и возвращает обновленной записи.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: d2b089e8a7fc5c7ee26139003e23d2eaa8a3174e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197404"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="58593-103">Копирование и обновление выражений записей</span><span class="sxs-lookup"><span data-stu-id="58593-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="58593-104">Объект *копирование и обновление выражений записей* выражение, которое копирует существующую запись, затем обновляет указанные поля и возвращает обновленной записи.</span><span class="sxs-lookup"><span data-stu-id="58593-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="58593-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58593-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="58593-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="58593-106">Remarks</span></span>

<span data-ttu-id="58593-107">Записи являются неизменяемыми по умолчанию, таким образом, возможна по существующей записи не обновляются.</span><span class="sxs-lookup"><span data-stu-id="58593-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="58593-108">Для создания обновленной записи все поля записи придется задать снова.</span><span class="sxs-lookup"><span data-stu-id="58593-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="58593-109">Для упрощения этой задачи *копирование и обновление выражений записей* может использоваться.</span><span class="sxs-lookup"><span data-stu-id="58593-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="58593-110">Это выражение принимает существующую запись, создает новый того же типа, используя указанные поля из выражения и отсутствует поле, указанных с помощью выражения.</span><span class="sxs-lookup"><span data-stu-id="58593-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="58593-111">Это может быть полезно, если необходимо скопировать существующую запись и при необходимости измените некоторые значения поля.</span><span class="sxs-lookup"><span data-stu-id="58593-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="58593-112">Возьмем например созданной записи.</span><span class="sxs-lookup"><span data-stu-id="58593-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="58593-113">Если пришлось обновлять только в поле этой записи можно использовать *копирование и обновление выражений записей* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="58593-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="58593-114">См. также</span><span class="sxs-lookup"><span data-stu-id="58593-114">See also</span></span>

- [<span data-ttu-id="58593-115">Записи</span><span class="sxs-lookup"><span data-stu-id="58593-115">Records</span></span>](records.md)
- [<span data-ttu-id="58593-116">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="58593-116">F# Language Reference</span></span>](index.md)

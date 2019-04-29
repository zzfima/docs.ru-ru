---
title: Переменная использует тип автоматизации, не поддерживаемый в Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: d369930752989ff69ee17359e85118f3af4b70b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766900"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a><span data-ttu-id="e23b3-102">Переменная использует тип автоматизации, не поддерживаемый в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e23b3-102">Variable uses an Automation type not supported in Visual Basic</span></span>

<span data-ttu-id="e23b3-103">Вы попытались использовать переменную, определенную в библиотеке типов или библиотекой объектов, с типом данных, не поддерживается в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e23b3-103">You tried to use a variable defined in a type library or object library that has a data type not supported by Visual Basic.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e23b3-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e23b3-104">To correct this error</span></span>

- <span data-ttu-id="e23b3-105">Используйте переменную типа распознаются Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e23b3-105">Use a variable of a type recognized by Visual Basic.</span></span>

     <span data-ttu-id="e23b3-106">-или-</span><span class="sxs-lookup"><span data-stu-id="e23b3-106">-or-</span></span>

- <span data-ttu-id="e23b3-107">Если эта ошибка возникает при использовании `FileGet` или `FileGetObject`, убедитесь, что вы пытаетесь использовать записи в файл с `FilePut` или `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="e23b3-107">If you encounter this error while using `FileGet` or `FileGetObject`, make sure the file you are trying to use was written to with `FilePut` or `FilePutObject`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e23b3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e23b3-108">See also</span></span>

- [<span data-ttu-id="e23b3-109">Типы данных</span><span class="sxs-lookup"><span data-stu-id="e23b3-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)

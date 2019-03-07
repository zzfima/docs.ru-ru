---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 670064084d3297a54b2860da3fe3acab00fa3ed8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469187"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="efd16-102">\<Возвращает > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efd16-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="efd16-103">Указывает возвращаемое значение свойства или функции.</span><span class="sxs-lookup"><span data-stu-id="efd16-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efd16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efd16-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="efd16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efd16-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="efd16-106">Описание возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="efd16-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efd16-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="efd16-107">Remarks</span></span>  
 <span data-ttu-id="efd16-108">Используйте `<returns>` тег в комментариях к объявлению метода для описания возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="efd16-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="efd16-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="efd16-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efd16-110">Пример</span><span class="sxs-lookup"><span data-stu-id="efd16-110">Example</span></span>  
 <span data-ttu-id="efd16-111">В этом примере используется `<returns>` тег, чтобы объяснить, что `DoesRecordExist` возврата функции.</span><span class="sxs-lookup"><span data-stu-id="efd16-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="efd16-112">См. также</span><span class="sxs-lookup"><span data-stu-id="efd16-112">See also</span></span>
- [<span data-ttu-id="efd16-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="efd16-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

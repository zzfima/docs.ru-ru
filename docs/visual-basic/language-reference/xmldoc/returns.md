---
title: '&lt;Возвращает&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 4dcf8e9aee6edecbda2874a6e07fbe6e3772b18b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580529"
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="e5f66-102">&lt;Возвращает&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5f66-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="e5f66-103">Указывает возвращаемое значение свойства или функции.</span><span class="sxs-lookup"><span data-stu-id="e5f66-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5f66-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5f66-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5f66-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="e5f66-106">Описание возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="e5f66-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5f66-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5f66-107">Remarks</span></span>  
 <span data-ttu-id="e5f66-108">Используйте `<returns>` тег в комментариях к объявлению метода для описания возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="e5f66-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="e5f66-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="e5f66-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5f66-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e5f66-110">Example</span></span>  
 <span data-ttu-id="e5f66-111">В этом примере используется `<returns>` тег, чтобы объяснить, что `DoesRecordExist` возврата функции.</span><span class="sxs-lookup"><span data-stu-id="e5f66-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e5f66-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e5f66-112">See also</span></span>
- [<span data-ttu-id="e5f66-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="e5f66-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

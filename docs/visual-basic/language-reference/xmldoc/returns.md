---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524684"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="016aa-102">> \<returns (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="016aa-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="016aa-103">Задает возвращаемое значение свойства или функции.</span><span class="sxs-lookup"><span data-stu-id="016aa-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="016aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="016aa-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="016aa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="016aa-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="016aa-106">Описание возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="016aa-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="016aa-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="016aa-107">Remarks</span></span>  
 <span data-ttu-id="016aa-108">Используйте тег `<returns>` в комментарии для объявления метода, чтобы описать возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="016aa-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="016aa-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="016aa-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="016aa-110">Пример</span><span class="sxs-lookup"><span data-stu-id="016aa-110">Example</span></span>  
 <span data-ttu-id="016aa-111">В этом примере используется тег `<returns>` для объяснения того, что возвращает функция `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="016aa-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="016aa-112">См. также</span><span class="sxs-lookup"><span data-stu-id="016aa-112">See also</span></span>

- [<span data-ttu-id="016aa-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="016aa-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

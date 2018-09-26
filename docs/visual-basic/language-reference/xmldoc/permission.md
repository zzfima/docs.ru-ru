---
title: '&lt;разрешение&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: bcec5d968f5d0c5400c28e772df151b164888a47
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205196"
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="d4d8b-102">&lt;разрешение&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4d8b-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="d4d8b-103">Указывает разрешение, необходимые для элемента.</span><span class="sxs-lookup"><span data-stu-id="d4d8b-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d8b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4d8b-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4d8b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4d8b-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="d4d8b-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="d4d8b-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="d4d8b-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="d4d8b-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="d4d8b-108">Заключите `member` в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="d4d8b-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d4d8b-109">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="d4d8b-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4d8b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4d8b-110">Remarks</span></span>  
 <span data-ttu-id="d4d8b-111">Используйте `<permission>` тег, чтобы документировать уровень доступа члена.</span><span class="sxs-lookup"><span data-stu-id="d4d8b-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="d4d8b-112">Используйте <xref:System.Security.PermissionSet> для задания доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="d4d8b-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="d4d8b-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="d4d8b-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4d8b-114">Пример</span><span class="sxs-lookup"><span data-stu-id="d4d8b-114">Example</span></span>  
 <span data-ttu-id="d4d8b-115">В этом примере используется `<permission>` тегов для описания, <xref:System.Security.Permissions.FileIOPermission> необходим `ReadFile` метод.</span><span class="sxs-lookup"><span data-stu-id="d4d8b-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d4d8b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d4d8b-116">See Also</span></span>  
 [<span data-ttu-id="d4d8b-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="d4d8b-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

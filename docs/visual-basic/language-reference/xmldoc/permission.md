---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: a8914e6d8fbce3e99ff92d9e4968e85a0f0ad7d5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263645"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="f192f-102">\<разрешение > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f192f-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="f192f-103">Указывает разрешение, необходимые для элемента.</span><span class="sxs-lookup"><span data-stu-id="f192f-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f192f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f192f-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f192f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f192f-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="f192f-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="f192f-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="f192f-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="f192f-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="f192f-108">Заключите `member` в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="f192f-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f192f-109">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="f192f-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f192f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f192f-110">Remarks</span></span>  
 <span data-ttu-id="f192f-111">Используйте `<permission>` тег, чтобы документировать уровень доступа члена.</span><span class="sxs-lookup"><span data-stu-id="f192f-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="f192f-112">Используйте <xref:System.Security.PermissionSet> для задания доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="f192f-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="f192f-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="f192f-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f192f-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f192f-114">Example</span></span>  
 <span data-ttu-id="f192f-115">В этом примере используется `<permission>` тегов для описания, <xref:System.Security.Permissions.FileIOPermission> необходим `ReadFile` метод.</span><span class="sxs-lookup"><span data-stu-id="f192f-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f192f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f192f-116">See also</span></span>
- [<span data-ttu-id="f192f-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="f192f-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

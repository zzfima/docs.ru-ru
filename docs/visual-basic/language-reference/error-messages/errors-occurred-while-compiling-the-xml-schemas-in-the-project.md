---
title: При компиляции XML-схем в проекте возникли ошибки
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 0cc565809792c619ca9903f9ef9b029b51a8aa17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="ef411-102">При компиляции XML-схем в проекте возникли ошибки</span><span class="sxs-lookup"><span data-stu-id="ef411-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="ef411-103">При компиляции схем XML в проекте возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="ef411-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="ef411-104">По этой причине недоступна технология XML IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ef411-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="ef411-105">Имеется ошибка в схеме определения схемы XML (XSD), включенный в проект.</span><span class="sxs-lookup"><span data-stu-id="ef411-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="ef411-106">Эта ошибка возникает при добавлении XSD-файл схемы (XSD), конфликтует с существующей схемой XSD задано для проекта.</span><span class="sxs-lookup"><span data-stu-id="ef411-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="ef411-107">**Идентификатор ошибки:** BC36810</span><span class="sxs-lookup"><span data-stu-id="ef411-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef411-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ef411-108">To correct this error</span></span>  
  
-   <span data-ttu-id="ef411-109">Дважды щелкните значок предупреждения в **список ошибок** окна.</span><span class="sxs-lookup"><span data-stu-id="ef411-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="ef411-110">Visual Basic, вы перейдете расположение в XSD-файле, который является источником предупреждения.</span><span class="sxs-lookup"><span data-stu-id="ef411-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="ef411-111">Исправьте ошибку в схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="ef411-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="ef411-112">Убедитесь, что все необходимые файлы XSD-схемы (XSD-файл) включены в проект.</span><span class="sxs-lookup"><span data-stu-id="ef411-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="ef411-113">Может потребоваться щелкните **Показать все файлы** на **проекта** меню для просмотра вашего .xsd файлы в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="ef411-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="ef411-114">Щелкните правой кнопкой мыши XSD-файл и нажмите кнопку **включить в проект** для включения файла в проекте.</span><span class="sxs-lookup"><span data-stu-id="ef411-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="ef411-115">Вы используете мастер построения схемы XML, эта ошибка может возникать при схемы были получены более одного раза из одного источника.</span><span class="sxs-lookup"><span data-stu-id="ef411-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="ef411-116">В этом случае можно удалить существующие файлы схемы XSD из проекта, добавьте новый XML-код для шаблона элементов схемы, а затем введите XML для мастера схем с всех источниками XML для проекта.</span><span class="sxs-lookup"><span data-stu-id="ef411-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="ef411-117">Если ошибка не найдена в схеме XSD, компилятору XML может не иметь достаточно сведений для предоставляют подробные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ef411-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="ef411-118">Возможно, вы сможете получить более подробные сведения об ошибке, если вы убедитесь, что пространства имен XML для файлов XSD-файл в проект, совпадают пространствами имен XML для XML-схемы в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef411-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef411-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ef411-119">See Also</span></span>  
 [<span data-ttu-id="ef411-120">Окно "Список ошибок"</span><span class="sxs-lookup"><span data-stu-id="ef411-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)  
 [<span data-ttu-id="ef411-121">XML</span><span class="sxs-lookup"><span data-stu-id="ef411-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)

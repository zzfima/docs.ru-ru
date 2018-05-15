---
title: Влияние изменения внешнего вида базовой формы
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: 7ba4a78395bb93caa1d1d86dc135825ca2a58845
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a><span data-ttu-id="a920e-102">Влияние изменения внешнего вида базовой формы</span><span class="sxs-lookup"><span data-stu-id="a920e-102">Effects of Modifying a Base Form&#39;s Appearance</span></span>
<span data-ttu-id="a920e-103">В процессе разработки приложения часто может потребоваться изменить внешний вид базовой формы, от которой наследуются другие формы проекта (или других проектов).</span><span class="sxs-lookup"><span data-stu-id="a920e-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="a920e-104">Во время разработки изменения внешнего вида базовой формы (будь то значения свойств либо добавление и удаление элементов управления) отражаются на наследуемых формах при построении проекта, содержащего базовую форму.</span><span class="sxs-lookup"><span data-stu-id="a920e-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="a920e-105">Просто сохранить изменения в базовой форме будет недостаточно.</span><span class="sxs-lookup"><span data-stu-id="a920e-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="a920e-106">Для сборки проекта выберите в меню **Сборка** пункт **Собрать**.</span><span class="sxs-lookup"><span data-stu-id="a920e-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a920e-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="a920e-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a920e-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="a920e-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a920e-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a920e-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
 <span data-ttu-id="a920e-110">Изменения, внесенные в базовую форму во время выполнения, не влияют на наследуемые формы, экземпляры которых уже созданы.</span><span class="sxs-lookup"><span data-stu-id="a920e-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a920e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a920e-111">See Also</span></span>  
 [<span data-ttu-id="a920e-112">base</span><span class="sxs-lookup"><span data-stu-id="a920e-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="a920e-113">Практическое руководство. Наследование форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a920e-113">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="a920e-114">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a920e-114">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)

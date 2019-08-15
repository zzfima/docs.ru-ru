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
ms.openlocfilehash: 5239017eb63ca6360ae8811a76497256fafbd1b1
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040134"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="cb7dc-102">Влияние изменения внешнего вида базовой формы</span><span class="sxs-lookup"><span data-stu-id="cb7dc-102">Effects of modifying a base form's appearance</span></span>

<span data-ttu-id="cb7dc-103">В процессе разработки приложения часто может потребоваться изменить внешний вид базовой формы, от которой наследуются другие формы проекта (или других проектов).</span><span class="sxs-lookup"><span data-stu-id="cb7dc-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>

<span data-ttu-id="cb7dc-104">Во время разработки изменения внешнего вида базовой формы (будь то значения свойств либо добавление и удаление элементов управления) отражаются на наследуемых формах при построении проекта, содержащего базовую форму.</span><span class="sxs-lookup"><span data-stu-id="cb7dc-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="cb7dc-105">Просто сохранить изменения в базовой форме будет недостаточно.</span><span class="sxs-lookup"><span data-stu-id="cb7dc-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="cb7dc-106">Для сборки проекта выберите в меню **Сборка** пункт **Собрать**.</span><span class="sxs-lookup"><span data-stu-id="cb7dc-106">To build a project, choose **Build** from the **Build** menu.</span></span>

<span data-ttu-id="cb7dc-107">Изменения, внесенные в базовую форму во время выполнения, не влияют на наследуемые формы, экземпляры которых уже созданы.</span><span class="sxs-lookup"><span data-stu-id="cb7dc-107">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb7dc-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cb7dc-108">See also</span></span>

- [<span data-ttu-id="cb7dc-109">base</span><span class="sxs-lookup"><span data-stu-id="cb7dc-109">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="cb7dc-110">Практическое руководство. Наследовать Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb7dc-110">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="cb7dc-111">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb7dc-111">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)

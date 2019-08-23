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
ms.openlocfilehash: b24bd2db564c7acb0a748c47095ee0777ea1eb88
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955147"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="0db76-102">Влияние изменения внешнего вида базовой формы</span><span class="sxs-lookup"><span data-stu-id="0db76-102">Effects of modifying a base form's appearance</span></span>

<span data-ttu-id="0db76-103">В процессе разработки приложения часто может потребоваться изменить внешний вид базовой формы, от которой наследуются другие формы проекта (или других проектов).</span><span class="sxs-lookup"><span data-stu-id="0db76-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>

<span data-ttu-id="0db76-104">Во время разработки изменения внешнего вида базовой формы (будь то значения свойств либо добавление и удаление элементов управления) отражаются на наследуемых формах при построении проекта, содержащего базовую форму.</span><span class="sxs-lookup"><span data-stu-id="0db76-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="0db76-105">Просто сохранить изменения в базовой форме будет недостаточно.</span><span class="sxs-lookup"><span data-stu-id="0db76-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="0db76-106">Для сборки проекта выберите в меню **Сборка** пункт **Собрать**.</span><span class="sxs-lookup"><span data-stu-id="0db76-106">To build a project, choose **Build** from the **Build** menu.</span></span>

<span data-ttu-id="0db76-107">Изменения, внесенные в базовую форму во время выполнения, не влияют на наследуемые формы, экземпляры которых уже созданы.</span><span class="sxs-lookup"><span data-stu-id="0db76-107">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>

## <a name="see-also"></a><span data-ttu-id="0db76-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0db76-108">See also</span></span>

- [<span data-ttu-id="0db76-109">base</span><span class="sxs-lookup"><span data-stu-id="0db76-109">base</span></span>](../../../csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="0db76-110">Практическое руководство. Наследовать Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0db76-110">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="0db76-111">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0db76-111">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)

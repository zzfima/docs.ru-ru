---
title: Советы по использованию элемента управления TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526457"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="80557-102">Советы по использованию элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="80557-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="80557-103"><xref:System.Windows.Forms.TableLayoutPanel> Управления предоставляет набор мощных функций, которые следует внимательно изучить перед использованием в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="80557-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="80557-104">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="80557-104">Recommendations</span></span>  
 <span data-ttu-id="80557-105">Следующие рекомендации помогут вам использовать <xref:System.Windows.Forms.TableLayoutPanel> управления ее преимущества.</span><span class="sxs-lookup"><span data-stu-id="80557-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="80557-106">Целевое использование</span><span class="sxs-lookup"><span data-stu-id="80557-106">Targeted Use</span></span>  
 <span data-ttu-id="80557-107">Используйте <xref:System.Windows.Forms.TableLayoutPanel> управлять только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="80557-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="80557-108">Его не следует использовать во всех ситуациях, для создания макетов.</span><span class="sxs-lookup"><span data-stu-id="80557-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="80557-109">В следующем списке описываются макеты, получить выгоду от использования <xref:System.Windows.Forms.TableLayoutPanel> управления:</span><span class="sxs-lookup"><span data-stu-id="80557-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="80557-110">Макеты, в которых состоит из нескольких частей формы, пропорциональное изменение размеров друг с другом.</span><span class="sxs-lookup"><span data-stu-id="80557-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="80557-111">Макеты, которые будут изменены или формируется динамически во время выполнения, например формы для ввода данных, имеющих настраиваемые поля, добавляется или вычитается на основе параметров.</span><span class="sxs-lookup"><span data-stu-id="80557-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="80557-112">Макеты, которые должны оставаться в общую фиксированный размер.</span><span class="sxs-lookup"><span data-stu-id="80557-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="80557-113">Например имеется диалоговым окном, которое должно остаться меньше, чем 800 x 600, но для поддержки локализованных строк.</span><span class="sxs-lookup"><span data-stu-id="80557-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="80557-114">В следующем списке описываются макеты, которые не выигрывают от использования значительно <xref:System.Windows.Forms.TableLayoutPanel> управления:</span><span class="sxs-lookup"><span data-stu-id="80557-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="80557-115">Простые формы ввода данных с одним столбцом меток и один столбец областей ввода текста.</span><span class="sxs-lookup"><span data-stu-id="80557-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="80557-116">Формы с одной большой областью отображения, которая должно заполнять все доступное пространство, при изменении размера.</span><span class="sxs-lookup"><span data-stu-id="80557-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="80557-117">Примером этого является форма, отображающая один <xref:System.Windows.Forms.PropertyGrid> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="80557-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="80557-118">В этом случае используйте привязку, так как ничего должны расширяться при изменении размера формы.</span><span class="sxs-lookup"><span data-stu-id="80557-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="80557-119">Тщательно выбирать, какие элементы управления должны быть <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="80557-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="80557-120">Если имеется достаточно места для увеличения на 30% с использованием привязки текста, рассмотрите возможность использования <xref:System.Windows.Forms.Control.Anchor%2A> только свойство.</span><span class="sxs-lookup"><span data-stu-id="80557-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="80557-121">Если можно оценить пространство, необходимое для макета, использование <xref:System.Windows.Forms.Control.Dock%2A> и <xref:System.Windows.Forms.Control.Anchor%2A> проще, чем оценка сведения оставшегося пространства и <xref:System.Windows.Forms.Control.AutoSize%2A> поведение.</span><span class="sxs-lookup"><span data-stu-id="80557-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="80557-122">В целом при разработке макета с <xref:System.Windows.Forms.TableLayoutPanel> контроля, упрощения разработки.</span><span class="sxs-lookup"><span data-stu-id="80557-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="80557-123">Используйте окно структуры документа</span><span class="sxs-lookup"><span data-stu-id="80557-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="80557-124">Окно «Структура документа» дает древовидное представление макета, в котором можно использовать для работы с z порядка и иерархические связи элементов управления.</span><span class="sxs-lookup"><span data-stu-id="80557-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="80557-125">Из **меню "Вид"** выберите **другие окна**, а затем выберите **Структура документа**.</span><span class="sxs-lookup"><span data-stu-id="80557-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="80557-126">Старайтесь не использовать</span><span class="sxs-lookup"><span data-stu-id="80557-126">Avoid Nesting</span></span>  
 <span data-ttu-id="80557-127">Старайтесь не использовать другие <xref:System.Windows.Forms.TableLayoutPanel> управления внутри <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="80557-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="80557-128">Отладка вложенных макетов может быть затруднено.</span><span class="sxs-lookup"><span data-stu-id="80557-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="80557-129">Избегайте визуального наследования</span><span class="sxs-lookup"><span data-stu-id="80557-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="80557-130"><xref:System.Windows.Forms.TableLayoutPanel> Управления не поддерживает визуальное наследование в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="80557-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="80557-131">Объект <xref:System.Windows.Forms.TableLayoutPanel> элемент управления в производном классе, как «заблокирован» во время разработки.</span><span class="sxs-lookup"><span data-stu-id="80557-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80557-132">См. также</span><span class="sxs-lookup"><span data-stu-id="80557-132">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>

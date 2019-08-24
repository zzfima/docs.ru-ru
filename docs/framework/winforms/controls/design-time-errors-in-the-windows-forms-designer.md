---
title: Ошибки во время разработки в конструкторе Windows Forms Designer
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015972"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="84a78-102">Ошибки времени разработки в конструктор Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84a78-102">Design-time errors in the Windows Forms Designer</span></span>

<span data-ttu-id="84a78-103">В этом разделе объясняется смысл и использование списка ошибок времени разработки, который отображается в Visual Studio, когда не удается загрузить конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="84a78-103">This topic explains the meaning and use of the design-time error list that appears in Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="84a78-104">При появления такого списка его надо использовать для исправлении ошибок в коде, а не воспринимать как ошибку в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="84a78-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>

<span data-ttu-id="84a78-105">Базовые знания об этом списке ошибок должны помочь при отладке приложений, так как вы получите подробные сведения об ошибках и будете знать возможные решения.</span><span class="sxs-lookup"><span data-stu-id="84a78-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>

## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="84a78-106">Интерфейс списка ошибок времени разработки</span><span class="sxs-lookup"><span data-stu-id="84a78-106">The design-time error list interface</span></span>

<span data-ttu-id="84a78-107">Если конструктор Windows Forms не удается загрузить, в конструкторе появится список ошибок.</span><span class="sxs-lookup"><span data-stu-id="84a78-107">If the Windows Forms Designer fails to load, an error list appears in the designer.</span></span> <span data-ttu-id="84a78-108">Ошибки группируются по категориям.</span><span class="sxs-lookup"><span data-stu-id="84a78-108">The errors are grouped into categories.</span></span> <span data-ttu-id="84a78-109">Например, при наличии четырех экземпляров необъявленных переменных они будут сгруппированы в одной категории ошибок.</span><span class="sxs-lookup"><span data-stu-id="84a78-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="84a78-110">Каждая категория ошибок содержит краткое описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="84a78-110">Each error category includes a brief description that summarizes the error.</span></span>

<span data-ttu-id="84a78-111">Категорию можно развернуть или свернуть, щелкнув заголовок категории ошибок либо шеврон развертывания или свертывания.</span><span class="sxs-lookup"><span data-stu-id="84a78-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="84a78-112">При развертывании категории ошибок отображается следующая дополнительная справка:</span><span class="sxs-lookup"><span data-stu-id="84a78-112">When you expand an error category, the following additional help is displayed:</span></span>

- <span data-ttu-id="84a78-113">Экземпляры ошибки;</span><span class="sxs-lookup"><span data-stu-id="84a78-113">Instances of this error.</span></span>

- <span data-ttu-id="84a78-114">Справка по ошибке;</span><span class="sxs-lookup"><span data-stu-id="84a78-114">Help with this error.</span></span>

- <span data-ttu-id="84a78-115">Сообщения об этой ошибке в форуме.</span><span class="sxs-lookup"><span data-stu-id="84a78-115">Forum posts about this error.</span></span>

### <a name="instances-of-this-error"></a><span data-ttu-id="84a78-116">Экземпляры этой ошибки</span><span class="sxs-lookup"><span data-stu-id="84a78-116">Instances of this error</span></span>

<span data-ttu-id="84a78-117">В дополнительной справке перечисляются все экземпляры ошибки в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="84a78-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="84a78-118">Многие ошибки содержат точное местоположение в следующем формате: *[имя_проекта]* *[имя формы]* строка: *[номер строки]* столбец: *[номер столбца]* .</span><span class="sxs-lookup"><span data-stu-id="84a78-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="84a78-119">По ссылке **Перейти к коду** можно перейти в расположение в коде, где произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="84a78-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>

<span data-ttu-id="84a78-120">Если с ошибкой связан стек вызовов, можно щелкнуть ссылку **Показать стек вызовов**, чтобы развернуть ошибку и показать стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="84a78-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="84a78-121">Благодаря анализу стека можно получить ценные отладочные сведения.</span><span class="sxs-lookup"><span data-stu-id="84a78-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="84a78-122">Например, можно отследить функции, которые были вызваны до возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="84a78-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="84a78-123">Стек вызовов можно выбрать, чтобы скопировать его и сохранить.</span><span class="sxs-lookup"><span data-stu-id="84a78-123">The call stack is selectable so that you can copy and save it.</span></span>

> [!NOTE]
> <span data-ttu-id="84a78-124">В Visual Basic в списке ошибок во время разработки отображается только одна ошибка, но в нем может отображаться несколько экземпляров одной и той же ошибки.</span><span class="sxs-lookup"><span data-stu-id="84a78-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="84a78-125">В Visual C++ ошибки не содержат ссылки для перехода к коду или к номеру строки.</span><span class="sxs-lookup"><span data-stu-id="84a78-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>

### <a name="forum-posts-about-this-error"></a><span data-ttu-id="84a78-126">Сообщения об этой ошибке в форуме</span><span class="sxs-lookup"><span data-stu-id="84a78-126">Forum posts about this error</span></span>

<span data-ttu-id="84a78-127">Дополнительная справка содержит ссылку на сообщения форума, связанные с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="84a78-127">The additional help includes a link to forum posts related to the error.</span></span> <span data-ttu-id="84a78-128">Поиск по форумам выполняется на основе строки сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="84a78-128">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="84a78-129">Также можно попробовать выполнить поиск на следующих форумах:</span><span class="sxs-lookup"><span data-stu-id="84a78-129">You can also try searching on the following forums:</span></span>

- [<span data-ttu-id="84a78-130">Форум конструктор Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84a78-130">Windows Forms Designer forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [<span data-ttu-id="84a78-131">Форум Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84a78-131">Windows Forms forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a><span data-ttu-id="84a78-132">Пропустить и продолжить</span><span class="sxs-lookup"><span data-stu-id="84a78-132">Ignore and continue</span></span>

<span data-ttu-id="84a78-133">Условие ошибки можно проигнорировать и продолжить загрузку конструктора.</span><span class="sxs-lookup"><span data-stu-id="84a78-133">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="84a78-134">Такое решение может привести к непредвиденному поведению.</span><span class="sxs-lookup"><span data-stu-id="84a78-134">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="84a78-135">Например, на поверхности разработки могут отсутствовать элементы управления.</span><span class="sxs-lookup"><span data-stu-id="84a78-135">For example, controls may not appear on the design surface.</span></span>

## <a name="see-also"></a><span data-ttu-id="84a78-136">См. также</span><span class="sxs-lookup"><span data-stu-id="84a78-136">See also</span></span>

- <span data-ttu-id="84a78-137">[Устранение неполадок разработки во время разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="84a78-137">[Troubleshooting Design-Time Development](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span></span>
- [<span data-ttu-id="84a78-138">Разрешение вопросов, связанных с созданием элементов управления и компонентов</span><span class="sxs-lookup"><span data-stu-id="84a78-138">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)
- [<span data-ttu-id="84a78-139">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="84a78-139">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- <span data-ttu-id="84a78-140">[Сообщения об ошибках конструктора Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="84a78-140">[Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span></span>

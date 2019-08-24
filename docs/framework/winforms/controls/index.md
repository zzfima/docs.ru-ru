---
title: Элементы управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls
- controls [Windows Forms]
- Windows Forms controls, about Windows Forms controls
ms.assetid: f050de8f-4ebd-4042-94b8-edf9a1dbd52a
ms.openlocfilehash: 1088781a7780df71773b01a3816f024562abfcaf
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69986979"
---
# <a name="windows-forms-controls"></a><span data-ttu-id="6948e-102">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6948e-102">Windows Forms controls</span></span>

<span data-ttu-id="6948e-103">При проектировании и изменении пользовательского интерфейса приложений Windows Forms, вам потребуется добавлять, выравнивать и размещать элементы управления.</span><span class="sxs-lookup"><span data-stu-id="6948e-103">As you design and modify the user interface of your Windows Forms applications, you will need to add, align, and position controls.</span></span> <span data-ttu-id="6948e-104">Элементы управления — это объекты, содержащиеся в объектах форм.</span><span class="sxs-lookup"><span data-stu-id="6948e-104">Controls are objects that are contained within form objects.</span></span> <span data-ttu-id="6948e-105">Каждый тип элемента управления имеет собственный набор свойств, методов и событий для достижения определенной цели.</span><span class="sxs-lookup"><span data-stu-id="6948e-105">Each type of control has its own set of properties, methods, and events that make it suitable for a particular purpose.</span></span> <span data-ttu-id="6948e-106">Вы можете управлять элементами управления в конструкторе и писать код для динамического добавления элементов управления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6948e-106">You can manipulate controls in the designer and write code to add controls dynamically at run time.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6948e-107">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="6948e-107">In this section</span></span>

<span data-ttu-id="6948e-108">[Размещение элементов управления в формах Windows Forms](putting-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6948e-108">[Putting Controls on Windows Forms](putting-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="6948e-109">Ссылки, связанные с размещением элементов управления в формах.</span><span class="sxs-lookup"><span data-stu-id="6948e-109">Provides links related to putting controls on forms.</span></span>

<span data-ttu-id="6948e-110">[Упорядочивание элементов управления в Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6948e-110">[Arranging Controls on Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="6948e-111">Статьи, связанные с упорядочиванием элементов управления в формах.</span><span class="sxs-lookup"><span data-stu-id="6948e-111">Articles related to arranging controls on forms.</span></span>

<span data-ttu-id="6948e-112">[Добавление меток к отдельным элементам управления Windows Forms и предоставление им ярлыков](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span><span class="sxs-lookup"><span data-stu-id="6948e-112">[Labeling Individual Windows Forms Controls and Providing Shortcuts to Them](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span></span>\
<span data-ttu-id="6948e-113">Использование сочетаний клавиш, текстовых меток на элементах управления, а также клавиш-модификаторов.</span><span class="sxs-lookup"><span data-stu-id="6948e-113">Describes the uses of keyboard shortcuts, text labels on controls, and modifier keys.</span></span>

<span data-ttu-id="6948e-114">[Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6948e-114">[Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md)</span></span>\
<span data-ttu-id="6948e-115">Список элементов управления, которые работают с Windows Forms, а также основные действия, которые можно выполнить с каждым элементом.</span><span class="sxs-lookup"><span data-stu-id="6948e-115">Lists the controls that work with Windows Forms, and basic things you can accomplish with each control.</span></span>

<span data-ttu-id="6948e-116">[Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="6948e-116">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="6948e-117">Дополнительные сведения и образцы, которые помогут вам в разработке пользовательских элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6948e-117">Provides background information and samples to help users develop custom Windows Forms controls.</span></span>

<span data-ttu-id="6948e-118">[Создание элементов управления Windows Forms во время разработки](developing-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="6948e-118">[Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="6948e-119">Способы создания пользовательских элементов управления с помощью проектирования и наследования.</span><span class="sxs-lookup"><span data-stu-id="6948e-119">Describes techniques for creating custom controls through design and inheritance.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6948e-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6948e-120">Related sections</span></span>

<span data-ttu-id="6948e-121">[Клиентские приложения](../../develop-client-apps.md)</span><span class="sxs-lookup"><span data-stu-id="6948e-121">[Client Applications](../../develop-client-apps.md)</span></span>\
<span data-ttu-id="6948e-122">Сведения о разработке приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="6948e-122">Provides an overview of developing Windows-based applications.</span></span>

---
title: Приложения с интерфейсом MDI
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0ce7c66946d03d566b21473711cb6b3315885236
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61952052"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="5d920-102">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="5d920-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="5d920-103">Приложения многодокументного интерфейса (MDI) позволяют отображать несколько документов в то же время, при этом каждый документ отображается в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="5d920-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="5d920-104">MDI приложения часто попадают в окно меню с вложенными меню для переключения между окнами или документами.</span><span class="sxs-lookup"><span data-stu-id="5d920-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d920-105">Существуют некоторые поведения различия между MDI-форм и однооконным интерфейсом (SDI) windows в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5d920-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="5d920-106">`Opacity` Свойство не влияет на внешний вид дочерних MDI-форм.</span><span class="sxs-lookup"><span data-stu-id="5d920-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="5d920-107">Кроме того <xref:System.Windows.Forms.Form.CenterToParent%2A> метод не влияет на поведение дочерних MDI-форм.</span><span class="sxs-lookup"><span data-stu-id="5d920-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d920-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5d920-108">In This Section</span></span>  
 [<span data-ttu-id="5d920-109">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="5d920-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="5d920-110">Указания по созданию контейнера для нескольких документов в приложении MDI.</span><span class="sxs-lookup"><span data-stu-id="5d920-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="5d920-111">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="5d920-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="5d920-112">Указания по созданию один или несколько окон, работающих в родительской формы MDI.</span><span class="sxs-lookup"><span data-stu-id="5d920-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="5d920-113">Практическое руководство. Определить активную дочернюю форму MDI</span><span class="sxs-lookup"><span data-stu-id="5d920-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="5d920-114">Указания по проверке дочернее окно с фокусом (и отправка его содержимое в буфер обмена).</span><span class="sxs-lookup"><span data-stu-id="5d920-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="5d920-115">Практическое руководство. Отправки данных в активную дочернюю форму MDI</span><span class="sxs-lookup"><span data-stu-id="5d920-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="5d920-116">Указания по передаче сведений в активное дочернее окно.</span><span class="sxs-lookup"><span data-stu-id="5d920-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="5d920-117">Практическое руководство. Упорядочение дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="5d920-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="5d920-118">Инструкции для заполнения каскадных и упорядочивание дочерних окон MDI-приложения.</span><span class="sxs-lookup"><span data-stu-id="5d920-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>

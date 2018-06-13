---
title: Приложения с интерфейсом MDI
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 3fa6f2517b52ecaaf4ad9db4f0de55908eac4c96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523972"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="d9a6c-102">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="d9a6c-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="d9a6c-103">Приложения многодокументного интерфейса (MDI) позволяют отображать несколько документов одновременно, при этом каждый документ отображается в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="d9a6c-104">MDI-приложения часто содержат элементы меню Window с вложенным меню для переключения между окнами или документами.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9a6c-105">Существуют некоторые различия MDI-форм и windows однооконный интерфейс (SDI) в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="d9a6c-106">`Opacity` Свойства не влияет на внешний вид дочерних MDI-форм.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="d9a6c-107">Кроме того <xref:System.Windows.Forms.Form.CenterToParent%2A> метод не влияет на поведение дочерних MDI-форм.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9a6c-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d9a6c-108">In This Section</span></span>  
 [<span data-ttu-id="d9a6c-109">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="d9a6c-109">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="d9a6c-110">Указания по созданию контейнера для нескольких документов в приложении MDI.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="d9a6c-111">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="d9a6c-111">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="d9a6c-112">Указания по созданию одного или нескольких окон, действующих в родительской формы MDI.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="d9a6c-113">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="d9a6c-113">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="d9a6c-114">Указания по проверке дочернее окно, в котором фокус (и как отправить содержимое в буфер обмена).</span><span class="sxs-lookup"><span data-stu-id="d9a6c-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="d9a6c-115">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="d9a6c-115">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="d9a6c-116">Указания по передаче сведений в активное дочернее окно.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="d9a6c-117">Практическое руководство. Упорядочение дочерних форм интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="d9a6c-117">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="d9a6c-118">Указания по мозаичное заполнение каскадные и упорядочение дочерних окон MDI-приложения.</span><span class="sxs-lookup"><span data-stu-id="d9a6c-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>

---
title: Общие сведения о компоненте SaveFileDialog
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743099"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="83f07-102">Общие сведения о компоненте SaveFileDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="83f07-102">SaveFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="83f07-103">Компонент Windows Forms <xref:System.Windows.Forms.SaveFileDialog> является стандартным диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="83f07-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="83f07-104">Это то же самое, что и стандартное диалоговое окно « **Сохранение файла** », используемое Windows.</span><span class="sxs-lookup"><span data-stu-id="83f07-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="83f07-105">Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="83f07-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="83f07-106">Работа с компонентом SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="83f07-106">Working with the SaveFileDialog Component</span></span>

<span data-ttu-id="83f07-107">Используйте его как простое решение, позволяющее пользователям сохранять файлы вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="83f07-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="83f07-108">Полагаться на стандартные диалоговые окна Windows, основные функциональные возможности создаваемых приложений будут сразу же знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="83f07-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="83f07-109">Однако имейте в виду, что при использовании компонента <xref:System.Windows.Forms.SaveFileDialog> необходимо написать собственную логику сохранения файлов.</span><span class="sxs-lookup"><span data-stu-id="83f07-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>

<span data-ttu-id="83f07-110">Для вывода диалогового окна во время выполнения можно использовать метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="83f07-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="83f07-111">Файл можно открыть в режиме чтения и записи с помощью метода <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="83f07-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>

<span data-ttu-id="83f07-112">При добавлении в форму <xref:System.Windows.Forms.SaveFileDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="83f07-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="83f07-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="83f07-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="83f07-114">Компонент SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="83f07-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)

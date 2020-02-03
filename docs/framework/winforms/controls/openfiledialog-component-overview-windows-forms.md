---
title: Общие сведения о компоненте OpenFileDialog
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728434"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="cd468-102">Общие сведения о компоненте OpenFileDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cd468-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="cd468-103">Компонент Windows Forms <xref:System.Windows.Forms.OpenFileDialog> является стандартным диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="cd468-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="cd468-104">Это то же диалоговое окно **открытия файла** , которое предоставляется операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="cd468-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="cd468-105">Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="cd468-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="cd468-106">Использовать этот компонент</span><span class="sxs-lookup"><span data-stu-id="cd468-106">Use this component</span></span>

<span data-ttu-id="cd468-107">Используйте этот компонент в приложении Windows в качестве простого решения для выбора файлов вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="cd468-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="cd468-108">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="cd468-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="cd468-109">Однако имейте в виду, что при использовании компонента <xref:System.Windows.Forms.OpenFileDialog> необходимо написать собственную логику открытия файлов.</span><span class="sxs-lookup"><span data-stu-id="cd468-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="cd468-110">Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для вывода диалогового окна во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cd468-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="cd468-111">Можно разрешить пользователям выбирать несколько файлов для открытия с помощью свойства <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd468-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="cd468-112">Кроме того, можно использовать свойство <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>, чтобы определить, отображается ли флажок только для чтения в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="cd468-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="cd468-113">Свойство <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> указывает, установлен ли флажок только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cd468-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="cd468-114">Наконец, свойство <xref:System.Windows.Forms.FileDialog.Filter%2A> задает текущую строку фильтра имен файлов, которая определяет варианты, отображаемые в поле "тип файлов" диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="cd468-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="cd468-115">При добавлении в форму <xref:System.Windows.Forms.OpenFileDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cd468-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd468-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cd468-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="cd468-117">Компонент OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="cd468-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)

---
title: Общие сведения о компоненте OpenFileDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: 24327ded50ac927642e2687b40b1f10de9bdf41e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211702"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="1dd25-102">Общие сведения о компоненте OpenFileDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1dd25-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="1dd25-103">Компонент Windows Forms <xref:System.Windows.Forms.OpenFileDialog> является стандартным диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="1dd25-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="1dd25-104">Он аналогичен **открыть файл** диалоговое окно, предоставляемые операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="1dd25-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="1dd25-105">Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="1dd25-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="1dd25-106">Использовать этот компонент</span><span class="sxs-lookup"><span data-stu-id="1dd25-106">Use this component</span></span>

<span data-ttu-id="1dd25-107">Этот компонент используется в приложении Windows в качестве простого решения для выбора файлов вместо настройки собственного диалогового.</span><span class="sxs-lookup"><span data-stu-id="1dd25-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="1dd25-108">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="1dd25-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="1dd25-109">Однако имейте в виду, что при с помощью <xref:System.Windows.Forms.OpenFileDialog> компонента, необходимо написать свою собственную логику для открытия файла.</span><span class="sxs-lookup"><span data-stu-id="1dd25-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="1dd25-110">Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод для отображения диалогового окна во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1dd25-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="1dd25-111">Можно разрешить пользователям выбрать несколько файлов для открытия с <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1dd25-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="1dd25-112">Кроме того, можно использовать <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> свойства, чтобы определить, если в диалоговом окне отображается флажок только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1dd25-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="1dd25-113"><xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Свойство указывает, установлен ли флажок «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="1dd25-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="1dd25-114">Наконец <xref:System.Windows.Forms.FileDialog.Filter%2A> свойство задает текущий строку фильтра имен файлов, которая определяет варианты, которые отображаются в поле «Тип файлов» в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="1dd25-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="1dd25-115">При добавлении в форму, <xref:System.Windows.Forms.OpenFileDialog> компонент появится в области в нижней части конструктора Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1dd25-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dd25-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1dd25-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="1dd25-117">Компонент OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="1dd25-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)

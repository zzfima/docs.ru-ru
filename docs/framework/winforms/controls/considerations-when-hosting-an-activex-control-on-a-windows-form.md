---
title: "Вопросы размещения элемента управления ActiveX в форме Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 23c8476e4013cca6d906d85f11658deddc585869
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a><span data-ttu-id="2752f-102">Вопросы размещения элемента управления ActiveX в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2752f-102">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>
<span data-ttu-id="2752f-103">Несмотря на то что формы Windows Forms оптимизированы для размещения элементов управления Windows Forms, в формах также можно использовать элементы управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="2752f-103">Although Windows Forms have been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="2752f-104">При планировании приложения, использующего элементы управления ActiveX, необходимо учитывать следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="2752f-104">Keep the following considerations in mind when planning an application that uses ActiveX controls:</span></span>  
  
-   <span data-ttu-id="2752f-105">**Безопасность**. Среда CLR была усовершенствована с точки зрения безопасности доступа для кода.</span><span class="sxs-lookup"><span data-stu-id="2752f-105">**Security** The common language runtime has been enhanced with regard to code access security.</span></span> <span data-ttu-id="2752f-106">Приложения, использующие Windows Forms, могут выполняться в полностью доверенной среде без каких-либо проблем и в среде с частичным доверием с большинством функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="2752f-106">Applications featuring Windows Forms can run in a fully trusted environment without issue and in a semi-trusted environment with most of the functionality accessible.</span></span> <span data-ttu-id="2752f-107">Элементы управления Windows Forms поддерживают размещение в браузере безо всяких сложностей.</span><span class="sxs-lookup"><span data-stu-id="2752f-107">Windows Forms controls can be hosted in a browser with no complications.</span></span> <span data-ttu-id="2752f-108">Тем не менее элементы управления ActiveX в Windows Forms не могут использовать преимущества этих улучшений безопасности.</span><span class="sxs-lookup"><span data-stu-id="2752f-108">However, ActiveX controls on Windows Forms cannot take advantage of these security enhancements.</span></span> <span data-ttu-id="2752f-109">Запуск элемента ActiveX требует разрешение неуправляемого кода, который устанавливается с <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="2752f-109">Running an ActiveX control requires unmanaged code permission, which is set with the <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2752f-110">Дополнительные сведения о безопасности и разрешениях неуправляемого кода см. в разделе <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2752f-110">For more information about security and unmanaged code permission, see <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span></span>  
  
-   <span data-ttu-id="2752f-111">**Общая стоимость владения**. Элементы управления ActiveX, добавляемые в форму Windows Forms, развертываются с помощью этой формы полностью, что значительно увеличивает размер создаваемых файлов.</span><span class="sxs-lookup"><span data-stu-id="2752f-111">**Total Cost of Ownership** ActiveX controls added to a Windows Form are deployed with that Windows Form in their entirety, which can add significantly to the size of the file(s) created.</span></span> <span data-ttu-id="2752f-112">Кроме того, для использования элементов управления ActiveX в формах Windows Forms требуется запись в реестр.</span><span class="sxs-lookup"><span data-stu-id="2752f-112">Additionally, using ActiveX controls on Windows Forms requires writing to the registry.</span></span> <span data-ttu-id="2752f-113">Таким образом, они более активно вмешиваются в работу компьютера пользователя, чем элементы управления Windows Forms, которые этого не требуют.</span><span class="sxs-lookup"><span data-stu-id="2752f-113">This is more invasive to a user's computer than Windows Forms controls, which do not require this.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2752f-114">Работа с элементами управления ActiveX требует использования оболочки COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="2752f-114">Working with an ActiveX control requires the use of a COM interop wrapper.</span></span> <span data-ttu-id="2752f-115">Дополнительные сведения см. в разделе [COM-взаимодействие в Visual Basic и Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="2752f-115">For more information, see [COM Interoperability in Visual Basic and Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2752f-116">Если имя члена элемента управления ActiveX совпадает с именем, определенным в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], то программа импорта элементов управления ActiveX добавит префикс к имени члена **Ctl** при создании <xref:System.Windows.Forms.AxHost> производного класса.</span><span class="sxs-lookup"><span data-stu-id="2752f-116">If the name of a member of the ActiveX control matches a name defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], then the ActiveX Control Importer will prefix the member name with **Ctl** when it creates the <xref:System.Windows.Forms.AxHost> derived class.</span></span> <span data-ttu-id="2752f-117">Например, если элемент управления ActiveX содержит член с именем **Layout**, в производном от AxHost классе он будет переименован в **CtlLayout**, так как в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] задано событие **Layout**.</span><span class="sxs-lookup"><span data-stu-id="2752f-117">For example, if your ActiveX control has a member named **Layout**, it is renamed **CtlLayout** in the AxHost-derived class because the **Layout** event is defined within the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2752f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2752f-118">See Also</span></span>  
 [<span data-ttu-id="2752f-119">Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2752f-119">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="2752f-120">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="2752f-120">Code Access Security</span></span>](../../../../docs/framework/misc/code-access-security.md)  
 [<span data-ttu-id="2752f-121">Сравнение элементов управления и программируемых объектов в разных языках и библиотеках</span><span class="sxs-lookup"><span data-stu-id="2752f-121">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="2752f-122">Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2752f-122">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="2752f-123">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2752f-123">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)

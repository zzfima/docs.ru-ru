---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: ff68c30c4e58cebb70c59352593d7b084413dce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="getcustomui"></a><span data-ttu-id="91c71-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="91c71-102">GetCustomUI</span></span>
<span data-ttu-id="91c71-103">Вызывается PresentationHost.exe для получения пользовательских хода выполнения и сообщения об ошибках с узла, если реализовано.</span><span class="sxs-lookup"><span data-stu-id="91c71-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c71-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91c71-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91c71-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="91c71-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="91c71-106">[out] Указатель на сборку, содержащую пользовательский интерфейс узла предоставленный хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="91c71-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="91c71-107">[out] Имя класса, интерфейс пользователя хода выполнения на указанный узел меньшее [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] , что файл <xref:System.Windows.Controls.Page> — его элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="91c71-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="91c71-108">Этот класс находится в сборке, который задается параметром `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="91c71-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="91c71-109">[out] Указатель на сборку, содержащую пользовательский интерфейс об узле.</span><span class="sxs-lookup"><span data-stu-id="91c71-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="91c71-110">[out] Имя класса пользователя об узле интерфейса, предпочтительно XAML-файл с <xref:System.Windows.Controls.Page> — его элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="91c71-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="91c71-111">Этот класс находится в сборке, который задается параметром `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="91c71-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="91c71-112">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="91c71-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="91c71-113">Значение HRESULT: игнорируется.</span><span class="sxs-lookup"><span data-stu-id="91c71-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91c71-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="91c71-114">Remarks</span></span>  
 <span data-ttu-id="91c71-115">Ведущее приложение может иметь особую тему, которая может не соответствовать PresentationHost.exe по умолчанию пользовательских интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="91c71-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="91c71-116">Если это так, можно реализовать ведущее приложение [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) для возврата хода выполнения и ошибки пользовательские интерфейсы PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="91c71-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="91c71-117">Всегда будет вызывать PresentationHost.exe [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) перед использованием его пользовательские интерфейсы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91c71-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="91c71-118">Эта функция вызывается один раз во время инициализации PresentationHost элемента.</span><span class="sxs-lookup"><span data-stu-id="91c71-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c71-119">См. также</span><span class="sxs-lookup"><span data-stu-id="91c71-119">See Also</span></span>  
 [<span data-ttu-id="91c71-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="91c71-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)

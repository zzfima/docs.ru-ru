---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 30084143949d2243fd310448c52e6b861505ad66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947970"
---
# <a name="getcustomui"></a><span data-ttu-id="af23d-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="af23d-102">GetCustomUI</span></span>
<span data-ttu-id="af23d-103">Вызывается программой PresentationHost.exe для получения пользовательских ход выполнения и сообщения об ошибках из узла, если реализовано.</span><span class="sxs-lookup"><span data-stu-id="af23d-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af23d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af23d-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="af23d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="af23d-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="af23d-106">[out] Указатель на сборку, содержащую пользовательский интерфейс хода выполнения, предоставляемую узла.</span><span class="sxs-lookup"><span data-stu-id="af23d-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="af23d-107">[out] Имя класса, пользовательском интерфейсе ход выполнения, предоставляемую узла предпочтительно [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] файл с <xref:System.Windows.Controls.Page> является его элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="af23d-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="af23d-108">Этот класс находится в сборке, который задается параметром `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="af23d-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="af23d-109">[out] Указатель на сборку, содержащую пользовательский интерфейс об узле.</span><span class="sxs-lookup"><span data-stu-id="af23d-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="af23d-110">[out] Имя класса, то есть пользователем узла об интерфейсе, предпочтительно файл XAML с <xref:System.Windows.Controls.Page> является его элемент верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="af23d-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="af23d-111">Этот класс находится в сборке, который задается параметром `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="af23d-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="af23d-112">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="af23d-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="af23d-113">HRESULT: Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="af23d-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af23d-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="af23d-114">Remarks</span></span>  
 <span data-ttu-id="af23d-115">Ведущее приложение может иметь конкретной темы, могут не соответствовать PresentationHost.exe по умолчанию пользовательские интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="af23d-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="af23d-116">Если это так, можно реализовать ведущее приложение [GetCustomUI](getcustomui.md) для возврата ход выполнения и ошибки пользовательских интерфейсов PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="af23d-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="af23d-117">PresentationHost.exe всегда будет вызывать [GetCustomUI](getcustomui.md) перед использованием его пользовательские интерфейсы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="af23d-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="af23d-118">Эта функция вызывается один раз во время инициализации процесс PresentationHost элемента.</span><span class="sxs-lookup"><span data-stu-id="af23d-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af23d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="af23d-119">See also</span></span>

- [<span data-ttu-id="af23d-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="af23d-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)

---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005709"
---
# <a name="getcustomui"></a><span data-ttu-id="ae801-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="ae801-102">GetCustomUI</span></span>
<span data-ttu-id="ae801-103">Вызывается PresentationHost. exe для получения настраиваемого хода выполнения и сообщений об ошибках с узла, если они реализованы.</span><span class="sxs-lookup"><span data-stu-id="ae801-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae801-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae801-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae801-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae801-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="ae801-106">заполняет Указатель на сборку, содержащую пользовательский интерфейс хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="ae801-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="ae801-107">заполняет Имя класса, предоставляемого ведущим пользовательским интерфейсом выполнения, предпочтительнее XAML-файл с <xref:System.Windows.Controls.Page> является элементом верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="ae801-107">[out] The name of the class that is the host-supplied progress user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="ae801-108">Этот класс находится в сборке, заданной `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="ae801-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="ae801-109">заполняет Указатель на сборку, содержащую пользовательский интерфейс ошибки, предоставляемый узлом.</span><span class="sxs-lookup"><span data-stu-id="ae801-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="ae801-110">заполняет Имя класса, предоставляемого ведущим пользовательским интерфейсом ошибок, предпочтительный XAML-файл с <xref:System.Windows.Controls.Page> является элементом верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="ae801-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="ae801-111">Этот класс находится в сборке, заданной `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="ae801-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ae801-112">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ae801-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="ae801-113">HRESULT: игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ae801-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae801-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae801-114">Remarks</span></span>  
 <span data-ttu-id="ae801-115">Ведущее приложение может иметь определенную тему, которая может не соответствовать интерфейсу пользователя PresentationHost. exe по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae801-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="ae801-116">В этом случае ведущее приложение может реализовать [GetCustomUI](getcustomui.md) для возврата сведений о ходе выполнения и ошибок пользовательского интерфейса в PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="ae801-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="ae801-117">PresentationHost. exe всегда будет вызывать [GetCustomUI](getcustomui.md) перед использованием пользовательских интерфейсов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae801-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="ae801-118">Эта функция вызывается один раз во время инициализации PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="ae801-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae801-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae801-119">See also</span></span>

- [<span data-ttu-id="ae801-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="ae801-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)

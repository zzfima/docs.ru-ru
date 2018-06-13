---
title: Атрибут PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 896f7b24599b68f178d2a006e5ddc07278564bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546075"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="ab59c-102">Атрибут PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="ab59c-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="ab59c-103">Наборы <xref:System.Windows.Freezable.IsFrozen%2A> состояние `true` в содержащем <xref:System.Windows.Freezable> элемента.</span><span class="sxs-lookup"><span data-stu-id="ab59c-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="ab59c-104">Поведение по умолчанию для <xref:System.Windows.Freezable> без `PresentationOptions:Freeze` указан атрибут звучит <xref:System.Windows.Freezable.IsFrozen%2A> — `false` во время загрузки и в зависимости от Общие <xref:System.Windows.Freezable> поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ab59c-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ab59c-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="ab59c-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ab59c-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="ab59c-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="ab59c-107">Префикс пространства имен XML, который может быть любой допустимой префиксной строкой, в соответствии со спецификацией XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="ab59c-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="ab59c-108">Префикс `PresentationOptions` используется в целях идентификации в этой документации.</span><span class="sxs-lookup"><span data-stu-id="ab59c-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="ab59c-109">Элемент, который создает экземпляры любой производный класс от <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="ab59c-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab59c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab59c-110">Remarks</span></span>  
 <span data-ttu-id="ab59c-111">`Freeze` Атрибут является единственным атрибутом или другого элемента программирования, определенного в `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="ab59c-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="ab59c-112">`Freeze` Атрибут существует в этом специальном пространстве имен, поэтому он может быть назначен в качестве игнорируемого, используя [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) как часть объявлений корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="ab59c-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="ab59c-113">Причина, `Freeze` должен иметь возможность быть ignorable не так как все [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации процессора может замораживать <xref:System.Windows.Freezable> во время загрузки; эта возможность не является частью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] спецификации.</span><span class="sxs-lookup"><span data-stu-id="ab59c-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="ab59c-114">Возможность обработки `Freeze` специально создан атрибут для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессором, который обрабатывает [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="ab59c-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="ab59c-115">Атрибут не поддерживается для любого класса, и синтаксис атрибута не является расширяемым или изменяемые.</span><span class="sxs-lookup"><span data-stu-id="ab59c-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="ab59c-116">При реализации собственных [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, вы можете параллельно закрепление поведение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор при обработке `Freeze` атрибут <xref:System.Windows.Freezable> элементов во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="ab59c-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="ab59c-117">Любое значение для `Freeze` атрибут, отличный от `true` (без учета регистра) вызывает ошибку во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="ab59c-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="ab59c-118">(Указание `Freeze` атрибута `false` не является ошибкой, но он уже имеет значение по умолчанию, поэтому `false` не выполняет никаких действий).</span><span class="sxs-lookup"><span data-stu-id="ab59c-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab59c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ab59c-119">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="ab59c-120">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="ab59c-120">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="ab59c-121">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="ab59c-121">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)

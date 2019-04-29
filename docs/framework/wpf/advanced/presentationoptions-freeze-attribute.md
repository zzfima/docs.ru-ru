---
title: Атрибут PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772844"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="f1ecf-102">Атрибут PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="f1ecf-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="f1ecf-103">Наборы <xref:System.Windows.Freezable.IsFrozen%2A> состояние `true` в содержащем <xref:System.Windows.Freezable> элемент.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="f1ecf-104">Поведение по умолчанию для <xref:System.Windows.Freezable> без `PresentationOptions:Freeze` указан атрибут является то, что <xref:System.Windows.Freezable.IsFrozen%2A> — `false` во время загрузки и в зависимости от Общие <xref:System.Windows.Freezable> поведению во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="f1ecf-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="f1ecf-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f1ecf-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="f1ecf-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="f1ecf-107">Префикс пространства имен XML, который может быть любая строка допустимый префикс, в соответствии со спецификацией XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="f1ecf-108">Префикс `PresentationOptions` используется для идентификации в этой документации.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="f1ecf-109">Элемент, который создает экземпляр любой производный класс <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1ecf-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1ecf-110">Remarks</span></span>  
 <span data-ttu-id="f1ecf-111">`Freeze` Атрибут является единственным атрибутом или другого элемента программирования, определенного в `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="f1ecf-112">`Freeze` Атрибут существует в этом специальном пространстве имен, поэтому он может быть назначен в качестве игнорируемого, используя [mc: Ignorable-атрибут](mc-ignorable-attribute.md) как часть объявлений корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="f1ecf-113">Причина, `Freeze` должен иметь возможность быть ignorable — так как не все [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализаций обработчиков может замораживать <xref:System.Windows.Freezable> во время загрузки; эта возможность не является частью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] спецификации.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="f1ecf-114">Возможность обработки `Freeze` атрибут специально встроен в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессором, который обрабатывает [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для скомпилированных приложений.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="f1ecf-115">Атрибут не поддерживается для любого класса, и синтаксис атрибута не является расширяемым или модифицируемым.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="f1ecf-116">Если вы реализуете собственный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, вы можете параллельная замораживания поведение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора при обработке `Freeze` атрибут <xref:System.Windows.Freezable> элементов во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="f1ecf-117">Любое значение для `Freeze` отличное от атрибута `true` (без учета регистра) вызывает ошибку времени загрузки.</span><span class="sxs-lookup"><span data-stu-id="f1ecf-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="f1ecf-118">(Указание `Freeze` атрибут как `false` не является ошибкой, но это уже по умолчанию, поэтому `false` не выполняет никаких действий).</span><span class="sxs-lookup"><span data-stu-id="f1ecf-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ecf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f1ecf-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="f1ecf-120">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="f1ecf-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="f1ecf-121">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="f1ecf-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)

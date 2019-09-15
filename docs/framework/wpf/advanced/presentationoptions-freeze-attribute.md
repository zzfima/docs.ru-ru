---
title: Атрибут PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991426"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="54ac1-102">Атрибут PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="54ac1-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="54ac1-103"><xref:System.Windows.Freezable.IsFrozen%2A> Задает <xref:System.Windows.Freezable> состояние вэлементе,содержащемэлемент.`true`</span><span class="sxs-lookup"><span data-stu-id="54ac1-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="54ac1-104">Поведение по умолчанию <xref:System.Windows.Freezable> для `PresentationOptions:Freeze` без <xref:System.Windows.Freezable.IsFrozen%2A> `false` атрибута задается во время загрузки и зависит от общего <xref:System.Windows.Freezable> поведения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="54ac1-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="54ac1-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="54ac1-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="54ac1-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="54ac1-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="54ac1-107">Префикс пространства имен XML, который может быть любой допустимой строкой префикса, согласно спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="54ac1-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="54ac1-108">Префикс `PresentationOptions` используется для идентификации в этой документации.</span><span class="sxs-lookup"><span data-stu-id="54ac1-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="54ac1-109">Элемент, создающий экземпляр любого производного класса <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="54ac1-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54ac1-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="54ac1-110">Remarks</span></span>  
 <span data-ttu-id="54ac1-111">Атрибут является единственным атрибутом или другим программным элементом, определенным `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` в пространстве имен XML. `Freeze`</span><span class="sxs-lookup"><span data-stu-id="54ac1-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="54ac1-112">Атрибут существует в этом специальном пространстве имен, поэтому его можно назначить как игнорируемый, используя [атрибут MC: Ignorable](mc-ignorable-attribute.md) как часть объявлений корневого элемента. `Freeze`</span><span class="sxs-lookup"><span data-stu-id="54ac1-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="54ac1-113">Причина, по `Freeze` которой должна быть возможна возможность пропуска, заключается в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] том, что не все реализации процессоров <xref:System.Windows.Freezable> способны заморозить во время загрузки. Эта возможность не [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] входит в спецификацию.</span><span class="sxs-lookup"><span data-stu-id="54ac1-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="54ac1-114">Возможность обработки `Freeze` атрибута в частности встроена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор, обрабатывающий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] скомпилированные приложения.</span><span class="sxs-lookup"><span data-stu-id="54ac1-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="54ac1-115">Атрибут не поддерживается ни одним классом, а синтаксис атрибутов не является расширяемым или изменяемым.</span><span class="sxs-lookup"><span data-stu-id="54ac1-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="54ac1-116">При реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] собственного процессора можно выбрать параллельное поведение [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] при фиксации процессора при обработке `Freeze` атрибута <xref:System.Windows.Freezable> элементов во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="54ac1-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="54ac1-117">Любое значение атрибута, `Freeze` `true` Кроме (без учета регистра), приводит к ошибке времени загрузки.</span><span class="sxs-lookup"><span data-stu-id="54ac1-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="54ac1-118">(Указание `Freeze` атрибута как `false` не является ошибкой, но он уже является значением по умолчанию, поэтому параметру `false` не требуется ничего).</span><span class="sxs-lookup"><span data-stu-id="54ac1-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ac1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="54ac1-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="54ac1-120">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="54ac1-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="54ac1-121">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="54ac1-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)

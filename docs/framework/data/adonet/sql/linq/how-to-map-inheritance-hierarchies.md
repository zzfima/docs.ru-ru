---
title: Практическое руководство. Как сопоставить иерархии наследования
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 618abc8e681a6f43a1054d0ca2cec2fbdec853f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943562"
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="80964-102">Практическое руководство. Как сопоставить иерархии наследования</span><span class="sxs-lookup"><span data-stu-id="80964-102">How to: Map Inheritance Hierarchies</span></span>
<span data-ttu-id="80964-103">Чтобы реализовать сопоставление наследования в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов, как описано в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="80964-103">To implement inheritance mapping in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="80964-104">Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для отображения иерархий наследования.</span><span class="sxs-lookup"><span data-stu-id="80964-104">Developers using Visual Studio can use the Object Relational Designer to map inheritance hierarchies.</span></span> <span data-ttu-id="80964-105">См. практическое руководство по [ настроить наследование с использованием реляционного конструктора объектов](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="80964-105">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80964-106">Особые атрибуты или свойства подклассов не требуются.</span><span class="sxs-lookup"><span data-stu-id="80964-106">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="80964-107">Обратите особое внимание на то, что подклассы не имеют атрибута <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80964-107">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="80964-108">Сопоставление иерархий наследования</span><span class="sxs-lookup"><span data-stu-id="80964-108">To map an inheritance hierarchy</span></span>  
  
1. <span data-ttu-id="80964-109">Добавьте к корневому классу атрибут <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80964-109">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2. <span data-ttu-id="80964-110">Кроме того, в корневом классе необходимо добавить атрибут <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> для каждого класса в структуре иерархии.</span><span class="sxs-lookup"><span data-stu-id="80964-110">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3. <span data-ttu-id="80964-111">Определите свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> для каждого атрибута <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.</span><span class="sxs-lookup"><span data-stu-id="80964-111">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="80964-112">Это свойство содержит значение, которое отображается в столбце <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> таблицы базы данных и указывает, к какому классу или подклассу принадлежит эта строка данных.</span><span class="sxs-lookup"><span data-stu-id="80964-112">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4. <span data-ttu-id="80964-113">Добавьте также для каждого атрибута <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="80964-113">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="80964-114">Данное свойство содержит значение, которое указывает, на какой класс или подкласс указывает значение ключа.</span><span class="sxs-lookup"><span data-stu-id="80964-114">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5. <span data-ttu-id="80964-115">Добавьте свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> только к одному атрибуту <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="80964-115">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="80964-116">Это свойство служит для обозначения резервного сопоставления, если значение дискриминатора из таблицы базы данных не соответствует какому-либо <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> значению в сопоставлениях наследования.</span><span class="sxs-lookup"><span data-stu-id="80964-116">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6. <span data-ttu-id="80964-117">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> к атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80964-117">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="80964-118">Это свойство означает, что данный столбец содержит значение <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.</span><span class="sxs-lookup"><span data-stu-id="80964-118">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80964-119">Пример</span><span class="sxs-lookup"><span data-stu-id="80964-119">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80964-120">Если вы используете Visual Studio, можно использовать реляционный конструктор объектов для настройки наследования.</span><span class="sxs-lookup"><span data-stu-id="80964-120">If you are using Visual Studio, you can use the Object Relational Designer to configure inheritance.</span></span> <span data-ttu-id="80964-121">См. практическое руководство по [ Настройка наследования с использованием реляционного конструктора объектов](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="80964-121">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="80964-122">В следующем примере кода определяется корневой класс `Vehicle` и выполняются указанные выше шаги с целью описания иерархии для [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80964-122">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="80964-123">См. также</span><span class="sxs-lookup"><span data-stu-id="80964-123">See also</span></span>

- [<span data-ttu-id="80964-124">Поддержка наследования</span><span class="sxs-lookup"><span data-stu-id="80964-124">Inheritance Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)
- [<span data-ttu-id="80964-125">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="80964-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)

---
title: Защищенные члены
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="protected-members"></a><span data-ttu-id="a1509-102">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="a1509-102">Protected Members</span></span>
<span data-ttu-id="a1509-103">Защищенные члены сами по себе не имеют все расширения, но они могут сделать расширяемости через подклассы более широкими возможностями.</span><span class="sxs-lookup"><span data-stu-id="a1509-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="a1509-104">Они могут использоваться для предоставления дополнительной настройки параметров без излишне усложнения основных открытого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a1509-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="a1509-105">Framework конструкторы, должны Будьте внимательны с защищенных членов, поскольку имя «защищен» может предоставить заблуждение безопасности.</span><span class="sxs-lookup"><span data-stu-id="a1509-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="a1509-106">Любой пользователь может подкласс незапечатанного класса и доступ к защищенным членам, и таким образом те же защитного приемы программирования, используемый для открытых членов касаться защищенные члены.</span><span class="sxs-lookup"><span data-stu-id="a1509-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="a1509-107">**✓ Попробуйте** с помощью защищенные члены для расширенной настройки.</span><span class="sxs-lookup"><span data-stu-id="a1509-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="a1509-108">**✓ СДЕЛАТЬ** обрабатывать защищенные члены незапечатанных классов как открытые с целью анализа безопасности, документацию и совместимости.</span><span class="sxs-lookup"><span data-stu-id="a1509-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="a1509-109">Любой пользователь может наследовать от класса и обращаться к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="a1509-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="a1509-110">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="a1509-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a1509-111">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="a1509-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1509-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a1509-112">See Also</span></span>  
 [<span data-ttu-id="a1509-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="a1509-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="a1509-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="a1509-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

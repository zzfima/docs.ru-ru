---
title: "Защищенные члены"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c3aacd0f08641c01200f0b1791a78413a306590
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="protected-members"></a><span data-ttu-id="61410-102">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="61410-102">Protected Members</span></span>
<span data-ttu-id="61410-103">Защищенные члены сами по себе не имеют все расширения, но они могут сделать расширяемости через подклассы более широкими возможностями.</span><span class="sxs-lookup"><span data-stu-id="61410-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="61410-104">Они могут использоваться для предоставления дополнительной настройки параметров без излишне усложнения основных открытого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="61410-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="61410-105">Framework конструкторы, должны Будьте внимательны с защищенных членов, поскольку имя «защищен» может предоставить заблуждение безопасности.</span><span class="sxs-lookup"><span data-stu-id="61410-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="61410-106">Любой пользователь может подкласс незапечатанного класса и доступ к защищенным членам, и таким образом те же защитного приемы программирования, используемый для открытых членов касаться защищенные члены.</span><span class="sxs-lookup"><span data-stu-id="61410-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="61410-107">**✓ Попробуйте** с помощью защищенные члены для расширенной настройки.</span><span class="sxs-lookup"><span data-stu-id="61410-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="61410-108">**✓ СДЕЛАТЬ** обрабатывать защищенные члены незапечатанных классов как открытые с целью анализа безопасности, документацию и совместимости.</span><span class="sxs-lookup"><span data-stu-id="61410-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="61410-109">Любой пользователь может наследовать от класса и обращаться к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="61410-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="61410-110">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="61410-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="61410-111">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="61410-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61410-112">См. также</span><span class="sxs-lookup"><span data-stu-id="61410-112">See Also</span></span>  
 [<span data-ttu-id="61410-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="61410-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="61410-114">Разработка для расширяемости</span><span class="sxs-lookup"><span data-stu-id="61410-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

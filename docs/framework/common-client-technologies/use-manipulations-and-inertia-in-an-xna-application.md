---
title: Использование манипуляций и инерции в приложении XNA
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 70b8d0c5c098089b6f16ef817ff86698f68cf7c3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44248908"
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>Использование манипуляций и инерции в приложении XNA
В этой статье описывается, как можно использовать  обработку манипуляций и инерции в приложении Microsoft XNA для управления движением элементов игры. Прежде чем приступить к чтению этой статьи, следует ознакомиться со статьей [Общие сведения о манипуляциях и инерции](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md). Кроме того, потребуется знакомство с основными концепциями программирования XNA.  
  
 Для выполнения задач, описанных в этой статье, проект XNA должен ссылаться на сборку <xref:System.Windows.Input.Manipulations>, а чтобы проект мог ссылаться на сборки XNA, на вашем компьютере должен быть установлен пакет [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([скачать](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)).  
  
## <a name="overview-of-functionality"></a>Обзор функциональных возможностей  
 В этой статье показано, как создать пользовательский класс, представляющий элемент игры, который использует обработку манипуляций и инерции. Этот класс позволяет управлять элементом игры на экране, перетаскивая его с помощью мыши, а затем освобождая его. После освобождения обработка инерции сохраняет движение элемента, как будто он постепенно замедляется. Перемещение как линейное, так и угловое.  
  
 ![Приложение простых манипуляций и инерции.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")  
  
 Кроме того, создается пользовательская коллекция, управляющая несколькими элементами игры. Это упрощает обработку, требуемую классом Game XNA.   
  
 [Создание класса GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Создание класса Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Полные листинги кода](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Input.Manipulations>  
 [Общие сведения о манипуляциях и инерции](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)

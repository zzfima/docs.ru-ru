---
title: Локализация
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 89851c42570f301bee8a3eca744eb5d069347d4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120873"
---
# <a name="localization"></a>Локализация

Локализацией называется процесс преобразования ресурсов приложения в локализованные версии для конкретных языков и региональных параметров, которые приложение должно поддерживать. К этапу локализации следует приступать только после [проверки локализуемости](../../../docs/standard/globalization-localization/localizability-review.md), которая позволяет проверить готовность глобализованного приложения к локализации.

Готовое к локализации приложение разделяется на два логических блока. Один из них содержит все элементы пользовательского интерфейса, а другой — исполняемый код. Блок пользовательского интерфейса содержит только локализуемые элементы, например строки, сообщения об ошибках, диалоговые окна, пункты меню, внедренные объектные ресурсы и т. д. для нейтрального языка и региональных параметров. Блок кода содержит только код приложения, который будет одинаковым для всех поддерживаемых языков и региональных параметров. Общеязыковая среда выполнения поддерживает модель ресурсов вспомогательной сборки, в которой исполняемый код приложения отделен от его ресурсов. Более подробную информацию о реализации этой модели см. в статье [Ресурсы в .NET](../../../docs/framework/resources/index.md).

Для каждой локализованной версии приложения добавьте новую вспомогательную сборку, которая содержит локализованный блок пользовательского интерфейса, учитывающий все требования целевого языка и региональных параметров. Блок кода должен оставаться одинаковым для всех языков и региональных параметров. Объединение локализованной версии блока пользовательского интерфейса с блоком кода создает новую локализованную версию приложения.

В пакете средств разработки (SDK) Windows предоставляется редактор ресурсов Windows Forms (Winres.exe), позволяющий быстро локализовать ресурсы Windows Forms для целевых языков и региональных параметров. Сведения об использовании этого инструмента см. в статье [Winres.exe (редактор ресурсов Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).

## <a name="see-also"></a>См. также раздел

- [Глобализация и локализация](../../../docs/standard/globalization-localization/index.md)
- [Анализ локализуемости](../../../docs/standard/globalization-localization/localizability-review.md)
- [Глобализация](../../../docs/standard/globalization-localization/globalization.md)
- [Ресурсы в приложениях для настольных систем](../../../docs/framework/resources/index.md)

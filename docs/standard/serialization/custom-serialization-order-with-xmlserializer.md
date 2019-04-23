---
title: Порядок пользовательской сериализации с помощью XmlSerializer
ms.date: 03/30/2017
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
ms.openlocfilehash: f63d460163c33c4253cf565a5755babc1030164f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295042"
---
# <a name="custom-serialization-order-with-xmlserializer"></a>Порядок пользовательской сериализации с помощью XmlSerializer
[Скачать образец](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 В этом образце показано, как управлять порядком сериализации и десериализации элементов XML-сериализации.  
  
 Дополнительные сведения о сериализации см. в комментариях к исходному коду и в файлах build.proj.  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a>Сборка образца с использованием командной строки  
  
1. Откройте окно командной строки и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.  
  
2. В командной строке введите **msbuild CustomOrder.sln**.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Сборка образца с использованием Visual Studio  
  
1. Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.  
  
2. Дважды щелкните значок CustomOrder.sln, чтобы открыть файл в Visual Studio.  
  
3. В меню **Построение** выберите команду **Построить решение**.  
  
4. По умолчанию сборка образца приложения помещается в подкаталог \bin или \bin\Debug.  
  
## <a name="see-also"></a>См. также

- [Базовая сериализация](../../../docs/standard/serialization/basic-serialization.md)
- [Двоичная сериализация](../../../docs/standard/serialization/binary-serialization.md)
- [Управление сериализацией XML с использованием атрибутов](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [Введение в сериализацию XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Сериализация](../../../docs/standard/serialization/index.md)
- [Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)

---
title: Метод XmlReader. Креатесклреадер (System. XML)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: c65ef7c073175488c11c5e912a44d46fd4319209
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215453"
---
# <a name="xmlreadercreatesqlreader-method"></a>Метод XmlReader.CreateSqlReader

Создает новый экземпляр <xref:System.Xml.XmlReader>, используя заданный поток, параметры и контекстную информацию для анализа.

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a>Параметры

- `input` <xref:System.IO.Stream>  
  Поток, содержащий XML-данные.

- `settings` <xref:System.Xml.XmlReaderSettings>  
  Параметры нового экземпляра <xref:System.Xml.XmlReader>. Это значение может быть равно `null`.

- `inputContext` <xref:System.Xml.XmlParserContext>  
  Для синтаксического анализа фрагмента XML необходимы контекстные сведения. Это значение может быть равно `null`.

## <a name="returns"></a>Результаты

<xref:System.Xml.XmlReader>  
Объект, используемый для чтения данных XML в потоке.

## <a name="remarks"></a>Примечания

> [!WARNING]
> Метод `XmlReader.CreateSqlReader` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Xml>

**Сборка:** System. XML. dll

**.NET Framework версии:** Доступно с 2,0.

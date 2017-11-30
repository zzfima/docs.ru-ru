---
title: "Объект My.Resources"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords: My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b2a2de7229f59e7deea29fe4186a5e466459d9fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="myresources-object"></a>Объект My.Resources
Предоставляет свойства и классы для доступа к ресурсам приложения.  
  
## <a name="remarks"></a>Примечания  
 `My.Resources` Объект предоставляет доступ к ресурсам приложения и позволяет динамически извлекать ресурсы для приложения. Дополнительные сведения см. в разделе [управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 `My.Resources` Объект предоставляет только глобальные ресурсы. Он не предоставляет доступ к файлам ресурсов, связанных с формами. Для доступа к ресурсам формы из формы. Дополнительные сведения см. в разделе [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Можно получить доступ к файлы ресурсов для определенных языка и региональных параметров приложения из `My.Resources` объекта. По умолчанию `My.Resources` объект ищет ресурсы из файла ресурсов, который совпадает с языком и региональными параметрами, в <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> свойство. Однако можно переопределить это поведение и указать определенного языка и региональных параметров для использования для ресурсов. Дополнительные сведения см. в разделе [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Свойства  
 Свойства `My.Resources` объект предоставлять доступ только для чтения к ресурсам приложения. Чтобы добавить или удалить ресурсы, используйте **конструктора проектов**. Дополнительные сведения см. в разделе [как: добавлять или удалять ресурсы](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Получить доступ к ресурсам, добавляемые с помощью **конструктора проектов** с помощью `My.Resources.``resourceName`.  
  
 Можно также добавить или удалить файлы ресурсов, выбрав проект в **обозревателе решений** и щелкнув **Добавление нового элемента** или **Добавление существующего элемента** из  **Проект** меню. Можно получить доступ к ресурсам, добавленным таким образом с помощью `My.Resources.``resourceFileName`.`resourceName`.  
  
 Каждый ресурс имеет имя, категорию и значение, и эти параметры ресурсов определяют отображение свойства доступа к ресурсам в `My.Resources` объекта. Для ресурсов, добавленных в **конструктора проектов**:  
  
-   Имя определяет имя свойства  
  
-   Данные ресурсов являются значение свойства  
  
-   Категория определяет тип свойства:  
  
|Категория|Тип данных свойства|  
|---|---|  
|**Строки**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Изображения**|<xref:System.Drawing.Bitmap>|  
|**Значки**|<xref:System.Drawing.Icon>|  
|**Аудио**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream> Класс является производным от <xref:System.IO.Stream> класса, чтобы можно было использовать с методами, которые принимают потоки, такие как <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> метод.|  
|**Файлы**|-   [Строка](../../../visual-basic/language-reference/data-types/string-data-type.md) для текстовых файлов.<br />-   <xref:System.Drawing.Bitmap>для файлов изображений.<br />-   <xref:System.Drawing.Icon>значок файлов.<br />-   <xref:System.IO.UnmanagedMemoryStream>для звуковых файлов.|  
|**Другое**|Определяются данными в конструкторе **тип** столбца.|  
  
## <a name="classes"></a>Классы  
 `My.Resources` Объект представляет каждый файл ресурсов как класс с общими свойствами. Имя класса совпадает с именем файла ресурсов. Как описано в предыдущем разделе, ресурсы в файле ресурсов представляются как свойства в классе.  
  
## <a name="example"></a>Пример  
 В этом примере заголовок формы устанавливается строковый ресурс с именем `Form1Title` в файл ресурсов приложения. Для работы этого примера приложение должно иметь строку с именем `Form1Title` в файле ресурсов. Дополнительные сведения см. в разделе [как: добавлять или удалять ресурсы](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере задает значок формы на значок с именем `Form1Icon` , хранится в файле ресурсов приложения. Для работы этого примера приложение должно иметь значок с именем `Form1Icon` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере задает фоновое изображение формы изображение ресурса с именем `Form1Background`, который находится в файле ресурсов приложения. Для работы этого примера приложение должно иметь ресурс изображения `Form1Background` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере воспроизводится звук, который хранится в виде звукового ресурса с именем `Form1Greeting` в файле ресурсов приложения. Для работы этого примера приложение должно иметь звуковой ресурс с именем `Form1Greeting` в файле ресурсов. `My.Computer.Audio.Play` Метод доступен только для приложений Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Пример  
 Этот пример возвращает версию французского языка строковый ресурс приложения. Ресурс с именем `Message`. Чтобы изменить язык и региональные параметры, `My.Resources` использует объект, в примере используется <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Для работы этого примера приложение должно иметь строку с именем `Message` в его ресурсов файлов и приложений должны иметь версию файла ресурсов, Resources.fr-FR.resx французского языка. Дополнительные сведения см. в разделе [как: добавлять или удалять ресурсы](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Если приложение не имеет версию французского языка файла ресурсов, `My.Resource` объект извлекает ресурс из файла ресурсов культуры по умолчанию.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Добавление или удаление ресурсов](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)  
 [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet)  
 [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md)  
 [Пошаговое руководство: Локализация форм Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)

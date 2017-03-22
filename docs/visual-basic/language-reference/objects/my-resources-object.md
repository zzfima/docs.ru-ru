---
title: "Объект My.Resources | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
dev_langs:
- VB
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6ad5bd4e33438256719b59cb0936cf6bc8525ab1
ms.lasthandoff: 03/13/2017

---
# <a name="myresources-object"></a>Объект My.Resources
Предоставляет свойства и классы для доступа к ресурсам приложения.  
  
## <a name="remarks"></a>Примечания  
 `My.Resources` Объект предоставляет доступ к ресурсам приложения и позволяет динамически извлекать ресурсы для приложения. Дополнительные сведения см. в разделе [управление ресурсами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).  
  
 `My.Resources` Объект предоставляет только глобальные ресурсы. Он не обеспечивает доступа к файлам ресурсов, связанных с формами. Необходимо получить доступ к ресурсам формы из формы. Дополнительные сведения см. в разделе [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Получить доступ к файлам ресурсов для конкретных языка и региональных параметров приложения из `My.Resources` объекта. По умолчанию `My.Resources` объекта ищет ресурсы из файла ресурсов, который совпадает с языком и региональными параметрами в <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>свойство.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> Однако можно переопределить это поведение и указать определенного языка и региональных параметров для использования ресурсов. Дополнительные сведения см. в разделе [ресурсов в приложениях рабочего стола](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890).  
  
## <a name="properties"></a>Свойства  
 Свойства `My.Resources` объект предоставлять доступ только для чтения к ресурсам приложения. Чтобы добавить или удалить ресурсы, используйте **конструктора проектов**. Дополнительные сведения см. в разделе [как: добавлять или удалять ресурсы](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Доступны ресурсы, добавленные с помощью **конструктора проектов** с помощью `My.Resources.``resourceName`.  
  
 Можно также добавить или удалить файлы ресурсов, выбрав проект в **обозревателе решений** и щелкнув **Добавление нового элемента** или **добавить существующий элемент** из **проекта** меню. Получить доступ к ресурсам, добавленным таким образом с помощью `My.Resources.``resourceFileName`.`resourceName`.  
  
 Каждый ресурс имеет имя, категорию и значение, и эти параметры ресурсов определяют, как отображается свойство для доступа к ресурсу в `My.Resources` объекта. Для ресурсов, добавленных в **конструктора проектов**:  
  
-   Имя определяет имя свойства  
  
-   Данные ресурсов являются значение свойства  
  
-   Категория определяет тип свойства:  
  
|Категория|Тип данных свойства|  
|---|---|  
|**Строки**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Изображения**|<xref:System.Drawing.Bitmap></xref:System.Drawing.Bitmap>|  
|**Значки**|<xref:System.Drawing.Icon></xref:System.Drawing.Icon>|  
|**Аудио**|<xref:System.IO.UnmanagedMemoryStream></xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream>Класс является производным от <xref:System.IO.Stream>класса, чтобы можно было использовать с методами, принимающими потоки, такие как <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>метод.</xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> </xref:System.IO.Stream> </xref:System.IO.UnmanagedMemoryStream>|  
|**Файлы**|-   [Строка](../../../visual-basic/language-reference/data-types/string-data-type.md) для текстовых файлов.<br />- <xref:System.Drawing.Bitmap>файлов изображений.</xref:System.Drawing.Bitmap><br />- <xref:System.Drawing.Icon>файлов значков.</xref:System.Drawing.Icon><br />- <xref:System.IO.UnmanagedMemoryStream>звук.</xref:System.IO.UnmanagedMemoryStream>|  
|**Другое**|Определяются данными в конструкторе **тип** столбца.|  
  
## <a name="classes"></a>Классы  
 `My.Resources` Объект представляет каждый файл ресурсов как класс с общими свойствами. Имя класса совпадает с именем файла ресурсов. Как описано в предыдущем разделе, ресурсы в файле ресурсов представляются как свойства в классе.  
  
## <a name="example"></a>Пример  
 В этом примере заголовок формы устанавливается строковый ресурс с именем `Form1Title` в файле ресурсов приложения. Для работы этого примера приложение должно иметь строку с именем `Form1Title` в файле ресурсов. Дополнительные сведения см. в разделе [как: добавлять или удалять ресурсы](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).  
  
 [!code-vb[VbVbalrMyResources&#1;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере задает значок формы на значок с именем `Form1Icon` , хранятся в файле ресурсов приложения. Для работы этого примера приложение должно иметь значок с именем `Form1Icon` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources&#2;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере задает фоновое изображение формы ресурса изображения с именем `Form1Background`, который находится в файле ресурсов приложения. Для работы этого примера приложение должно иметь ресурс изображения с именем `Form1Background` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources&#3;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере воспроизводится звук, который хранится в виде звукового ресурса с именем `Form1Greeting` в файле ресурсов приложения. Для работы этого примера приложение должно иметь звукового ресурса с именем `Form1Greeting` в файле ресурсов. `My.Computer.Audio.Play` Метод доступен только для приложений Windows Forms.  
  
 [!code-vb[VbVbalrMyResources&#4;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере извлекается французскую версию строковый ресурс приложения. Ресурс с именем `Message`. Для изменения культуры, `My.Resources` использует объект, используемый в примере <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>  
  
 Для работы этого примера приложение должно иметь строку с именем `Message` в его ресурсе файл и приложение должны иметь версию файла ресурсов, Resources.fr-FR.resx французского языка. Дополнительные сведения см. в разделе [как: добавлять или удалять ресурсы](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Если приложение не имеет французскую версию файла ресурсов, `My.Resource` объект извлекает ресурс из файла ресурсов культуры по умолчанию.  
  
 [!code-vb[VbVbalrMyResources&#10;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: Добавление и удаление ресурсов](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [Управление ресурсами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)   
 [Ресурсы в приложениях для настольных систем](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)   
 [Пошаговое руководство: Локализация форм Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)

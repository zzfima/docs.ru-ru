---
title: Объект My.Resources
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 7f5d81194123ad2151a494a3cb79aa1955e0fdad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350330"
---
# <a name="myresources-object"></a>Объект My.Resources
Предоставляет свойства и классы для доступа к ресурсам приложения.  
  
## <a name="remarks"></a>Заметки  
 Объект `My.Resources` предоставляет доступ к ресурсам приложения и позволяет динамически получать ресурсы для приложения. Дополнительные сведения см. в разделе [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 Объект `My.Resources` предоставляет только глобальные ресурсы. Он не предоставляет доступ к файлам ресурсов, связанным с формами. Необходимо получить доступ к ресурсам формы из формы.  
  
 Доступ к файлам ресурсов, относящимся к языку и региональным параметрам приложения, можно получить из объекта `My.Resources`. По умолчанию объект `My.Resources` ищет ресурсы из файла ресурсов, соответствующие языку и региональным параметрам в свойстве <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>. Однако это поведение можно переопределить и указать конкретный язык и региональные параметры, которые будут использоваться для ресурсов. Дополнительные сведения см. в разделе [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Свойства  
 Свойства объекта `My.Resources` предоставляют доступ только для чтения к ресурсам приложения. Чтобы добавить или удалить ресурсы, используйте **Конструктор проектов**. Доступ к ресурсам, добавленным с помощью **конструктора проектов** , можно получить с помощью `My.Resources.`*resourceName*.  
  
 Можно также добавлять или удалять файлы ресурсов, выбрав проект в **Обозреватель решений** и выбрав пункт **Добавить новый элемент** или **Добавить существующий элемент** в меню **проект** . Доступ к ресурсам, добавленным таким способом, можно получить с помощью `My.Resources.`*ресаурцефиленаме*`.`*resourceName*.  
  
 Каждый ресурс имеет имя, категорию и значение, и эти параметры ресурсов определяют, как свойство для доступа к ресурсу отображается в объекте `My.Resources`. Для ресурсов, добавленных в **конструкторе проектов**:  
  
- Имя определяет имя свойства,  
  
- Данные ресурса являются значением свойства,  
  
- Категория определяет тип свойства:  
  
|Категория|Тип данных свойства|  
|---|---|  
|**Строки**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Изображения**|<xref:System.Drawing.Bitmap>|  
|**Значки**|<xref:System.Drawing.Icon>|  
|**Звук**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> Класс <xref:System.IO.UnmanagedMemoryStream> является производным от класса <xref:System.IO.Stream>, поэтому его можно использовать с методами, принимающими потоки, например метод <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>.|  
|**Файлы**|-   [строка](../../../visual-basic/language-reference/data-types/string-data-type.md) для текстовых файлов.<br />-   <xref:System.Drawing.Bitmap> для файлов изображений.<br />для файлов значков -   <xref:System.Drawing.Icon>.<br />-   <xref:System.IO.UnmanagedMemoryStream> звуковых файлов.|  
|**Другое**|Определяется сведениями в столбце **типа** конструктора.|  
  
## <a name="classes"></a>Классы  
 Объект `My.Resources` предоставляет каждый файл ресурсов как класс с общими свойствами. Имя класса совпадает с именем файла ресурсов. Как описано в предыдущем разделе, ресурсы в файле ресурсов предоставляются как свойства в классе.  
  
## <a name="example"></a>Пример  
 В этом примере заголовок формы задается строковым ресурсом с именем `Form1Title` в файле ресурсов приложения. Чтобы пример работал, приложение должно иметь строку с именем `Form1Title` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>Пример  
 В этом примере значок формы задается значком с именем `Form1Icon`, который хранится в файле ресурсов приложения. Чтобы пример работал, приложение должно иметь значок с именем `Form1Icon` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>Пример  
 В этом примере для фонового изображения формы задается ресурс изображения с именем `Form1Background`, который находится в файле ресурсов приложения. Чтобы этот пример работал, приложение должно иметь ресурс образа с именем `Form1Background` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>Пример  
 В этом примере воспроизводится звук, который хранится в виде звукового ресурса с именем `Form1Greeting` в файле ресурсов приложения. Чтобы пример работал, приложение должно иметь звуковой ресурс с именем `Form1Greeting` в файле ресурсов. Метод `My.Computer.Audio.Play` доступен только для Windows Forms приложений.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>Пример  
 В этом примере извлекается версия строкового ресурса приложения на французском языке. Ресурс называется `Message`. Чтобы изменить язык и региональные параметры, используемые объектом `My.Resources`, в примере используется <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Чтобы этот пример работал, приложение должно иметь строку с именем `Message` в файле ресурсов, а приложение должно иметь французскую версию языка и региональных параметров этого файла ресурсов, Resources.fr-FR. resx. Если приложение не имеет версию файла ресурсов для французского языка и региональных параметров, объект `My.Resource` извлекает ресурс из файла ресурсов языка и региональных параметров по умолчанию.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>См. также

- [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md)

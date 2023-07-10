# react-native-document-picker-example

```js
import RNFS from 'react-native-fs';
import DocumentPicker from 'react-native-document-picker';

;(async function(){
  const docs = await DocumentPicker.pick({
    allowMultiSelection: true,
    type: DocumentPicker.types.allFiles,
    copyTo: "cachesDirectory", // or "documentDirectory"
  });
  
  const doc = docs[0];

  const {
    fileCopyUri,
    name,
    uri,
    // size,
    type,
  } = doc;

  const stat = await RNFS.stat(fileCopyUri);

  const {
    path,
    originalFilepath,
    size,
    ctime,
    mtime,
    isFile,
    isDirectory,
  } = stat;

  ...

})();
```

#### Types
- DocumentPicker.types.allFiles: All document types, on Android this is */*, on iOS is public.item
- DocumentPicker.types.images: All image types
- DocumentPicker.types.plainText: Plain text files
- DocumentPicker.types.audio: All audio types
- DocumentPicker.types.pdf: PDF documents
- DocumentPicker.types.zip: Zip files
- DocumentPicker.types.csv: Csv files
- DocumentPicker.types.doc: doc files
- DocumentPicker.types.docx: docx files
- DocumentPicker.types.ppt: ppt files
- DocumentPicker.types.pptx: pptx files
- DocumentPicker.types.xls: xls files
- DocumentPicker.types.xlsx: xlsx files

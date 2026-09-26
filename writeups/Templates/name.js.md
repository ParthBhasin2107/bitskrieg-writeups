<%*
const folderName = tp.file.folder(false);
const cutIndex = folderName.indexOf("_by");
const newName = cutIndex !== -1 ? folderName.substring(0, cutIndex) : folderName;

if (newName) {
  await tp.file.rename(newName);
}
%>
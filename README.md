# Usefull code snippets
### format csvstring to array of objects

´´´
function csvToArray(csvString) {
  const rows = csvString.split("\n").map(row => row.trim());
  const headers = rows[0].split(";");
  const data = rows.slice(1).map(row => {
    const values = row.split(";");
    return headers.reduce((obj, header, index) => {
      obj[header] = values[index];
      return obj;
    }, {});
  });
  return data;
}

´´´

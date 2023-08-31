# nextjs-pdf
Create Nextjs PDF with ease



obj.autoTable({
  startX: 20,
  startY: 30,
  head: [['Name', 'City', 'Phone No.']],
  body: [
    ['Donna', 'New York', '8456210'],
    ['Rachel', 'Los Angeles', '7845521'],
    ['Harvey', 'Chicago', '9865371'],
  ],
  theme: 'striped', // Apply a striped theme
  headStyles: {
    fillColor: [100, 100, 255], // Set header cell background color
    textColor: 255, // Set header text color
  },
  bodyStyles: {
    textColor: [0, 0, 0], // Set body text color
  },
  columnStyles: {
    0: { fontStyle: 'bold' }, // Apply bold style to the first column
  },
  margin: { top: 60 },
  didDrawPage: function (data) {
    obj.text('Generated by jsPDF AutoTable', data.settings.margin.left, 10);
  },
});

# nextjs-pdf
Create Nextjs PDF with ease

SAMPLE

"use client"


import React from 'react';
import jsPDF from 'jspdf';
import 'jspdf-autotable';
import Image from 'next/image';
import styles from './page.module.css';

export default function Home() {
    function demo() {
        var obj = new jsPDF('landscape');

        // Add title heading
        obj.setFontSize(18);
        obj.text('Sample Table Report', 20, 20);

        // Create the table
        obj.setFontSize(12);
        obj.autoTable({
            startX: 30,
            startY: 40, // Adjust startY to make space for the title
            head: [['Name', 'City', 'Phone No.']],
            body: [
                ['Bambo', 'World', '07066279211'],
                ['Rachel', 'Los Angeles', '7845521'],
                ['Harvey', 'Chicago', '9865371'],
            ],
        });
        obj.save('example.pdf');
    }

    return (
        <div>
            <div className={styles.buttonContainer}>
                <button className={styles.customButton} onClick={demo}>
                    Download PDF
                </button>
            </div>
        </div>
    );
}




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

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Klim_exz
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            {
                InitializeComponent();
                InitializeUI();
            }

            private void InitializeComponent()
            {
                this.SuspendLayout();

                // ComboBox для выбора типа такси (грузовое/легковое)
                this.taxiTypeComboBox = new ComboBox
                {
                    DropDownStyle = ComboBoxStyle.DropDownList,
                    Items = { "Грузовое", "Легковое" },
                    Location = new System.Drawing.Point(120, 30),
                    Size = new System.Drawing.Size(150, 21)
                };

                // ComboBox для выбора класса обслуживания (эконом/VIP)
                this.carClassComboBox = new ComboBox
                {
                    DropDownStyle = ComboBoxStyle.DropDownList,
                    Items = { "Эконом", "VIP" },
                    Location = new System.Drawing.Point(120, 70),
                    Size = new System.Drawing.Size(150, 21)
                };

                // Label для отображения информации о выборе типа такси
                this.taxiTypeLabel = new Label
                {
                    AutoSize = true,
                    Location = new System.Drawing.Point(30, 30),
                    Text = "Выберите тип такси:"
                };

                // Label для отображения информации о выборе класса обслуживания
                this.carClassLabel = new Label
                {
                    AutoSize = true,
                    Location = new System.Drawing.Point(30, 70),
                    Text = "Выберите класс обслуживания:"
                };

                // Button для запуска процесса диспетчеризации
                this.dispatchButton = new Button
                {
                    Location = new System.Drawing.Point(120, 120),
                    Size = new System.Drawing.Size(150, 30),
                    Text = "Вызвать такси"
                };
                this.dispatchButton.Click += new EventHandler(DispatchButton_Click);

                // Добавление элементов управления на форму
                this.Controls.Add(taxiTypeComboBox);
                this.Controls.Add(carClassComboBox);
                this.Controls.Add(taxiTypeLabel);
                this.Controls.Add(carClassLabel);
                this.Controls.Add(dispatchButton);

                this.ResumeLayout(false);
            }

            private void InitializeUI()
            {
                // Настройка параметров элементов управления и их размещение на форме
                // Можешь добавить дополнительные настройки, стили и размещения по своему усмотрению
            }

            private void DispatchButton_Click(object sender, EventArgs e)
            {
                // Логика диспетчеризации
                // Тут ты можешь добавить код для обработки выбора типа и класса такси
            }

        }
    }

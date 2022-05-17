//---------------------------------------------------------------------------

#include <vcl.h>
#pragma hdrstop

#include "Unit1.h"
#include "Unit2.h"
//---------------------------------------------------------------------------
#pragma package(smart_init)
#pragma resource "*.dfm"

TForm1 *Form1;

AnsiString nazwaPliku="";

//---------------------------------------------------------------------------
__fastcall TForm1::TForm1(TComponent* Owner)
        : TForm(Owner)
{
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Button16Click(TObject *Sender)
{
        Button16->Visible=false;
        Button18->Visible=true;
        Panel4->Color=clGreen;
        LCD->Color=clMoneyGreen;
        Return->Visible=true;

}
//---------------------------------------------------------------------------
void __fastcall TForm1::Button18Click(TObject *Sender)
{
        Button16->Visible=true;
        Button18->Visible=false;
        Panel4->Color=clMaroon;
        LCD->Caption="";
        LCD->Color=clSilver;
        Return->Visible=false;
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Murzyski1Click(TObject *Sender)
{
        tresc->Color=clWindowText;
        tresc->Font->Color=clWindow;

        if(Murzyski1->Checked==false)
        {
                Murzyski1->Checked=true;
                Biay1->Checked=false;
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Biay1Click(TObject *Sender)
{
        tresc->Color=clWindow;
        tresc->Font->Color=clWindowText;

        if(Biay1->Checked==false)
        {
                Biay1->Checked=true;
                Murzyski1->Checked=false;
        }
}
void __fastcall TForm1::Trybzaawansowany1Click(TObject *Sender)
{
        if(PanelIN->Visible==false)
        {
                PanelIN->Visible=true;
                Trybzaawansowany1->Checked=true;
        }
        else
        {
                PanelIN->Visible=false;
                Trybzaawansowany1->Checked=true;
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Otwrz1Click(TObject *Sender)
{
        try
        {
                 if(OpenDialog1->Execute())
                {
                         tresc->Lines->LoadFromFile(OpenDialog1->FileName);
                         nazwaPliku=OpenDialog1->FileName;
                }
        }

        catch(...)
        {
                ShowMessage("B³¹d otwarcia pliku. Upewnij siê, ¿e plik istnieje na dysku!");
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::ZapiszjakoCtrls1Click(TObject *Sender)
{
        try
        {
                 if(SaveDialog1->Execute())
                {
                         tresc->Lines->SaveToFile(SaveDialog1->FileName);
                         nazwaPliku=SaveDialog1->FileName;
                }
        }

        catch(...)
        {
                ShowMessage("Zapis zakoñczy³ siê nie powodzeniem!");
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Zapisz1Click(TObject *Sender)
{
        if(nazwaPliku!="")
        {
                tresc->Lines->SaveToFile(nazwaPliku);
        }
        else // w przeciwnym wypadku musimy wskazac gdzie zapisac plik
        {
                //jesli jeszcze nie znasz nazyw pliku to wywo³aj funkcje onClick dla obiektu z menu g³ównego (MainMenu1) voida po lewej stronie
                Form1->ZapiszjakoCtrls1Click(MainMenu1);
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Nowy1Click(TObject *Sender)
{
        if(Application->MessageBox("Czy na pewno utworzyæ nowy plik?","PotwierdŸ",MB_YESNOCANCEL | MB_ICONQUESTION)==IDYES)
        {
                tresc->Lines->Clear();
                nazwaPliku="";
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::trescKeyDown(TObject *Sender, WORD &Key,
      TShiftState Shift)
{
         if(Shift.Contains(ssCtrl))
         {
                if((Key=='s')||(Key=='S'))
                {
                        Form1->Zapisz1Click(MainMenu1);
                }
         }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Exit1Click(TObject *Sender)
{
        if(Application->MessageBox("Czy na pewno zakoñczyc program?","PotwierdŸ",MB_YESNO | MB_ICONQUESTION)==IDYES)
        {
                Application->Terminate();
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::FormClose(TObject *Sender, TCloseAction &Action)
{
        if(Application->MessageBox("Czy na pewno zakoñczyc program?","PotwierdŸ",MB_YESNO | MB_ICONQUESTION)==IDNO)
        {
                Action=caNone; // Nie podejmuj rzadnych dzia³añ
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::WytnijCtrlX1Click(TObject *Sender)
{
        tresc->CutToClipboard(); // wytnij do schowka     
}
//---------------------------------------------------------------------------
void __fastcall TForm1::KopiujCtrlC1Click(TObject *Sender)
{
        tresc->CopyToClipboard(); // Kopiuje do schowka
}
//---------------------------------------------------------------------------
void __fastcall TForm1::WklejCtrlV1Click(TObject *Sender)
{
        tresc->PasteFromClipboard();      
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Zawijajwiersze1Click(TObject *Sender)
{
        if(Zawijajwiersze1->Checked==true)
        {
                Zawijajwiersze1->Checked=false;
                tresc->WordWrap=false;
                tresc->ScrollBars=ssBoth;
        }
        else
        {
                Zawijajwiersze1->Checked=true;
                tresc->WordWrap=true;
                tresc->ScrollBars=ssVertical;
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Czcionka1Click(TObject *Sender)
{
        if(FontDialog1->Execute())
        {
                //kroj
                tresc->Font->Name = FontDialog1->Font->Name;

                //kolor
                tresc->Font->Color = FontDialog1->Font->Color;

                //rozmiar
                tresc->Font->Size = FontDialog1->Font->Size;

                //Styl
                tresc->Font->Style = FontDialog1->Font->Style;
        }
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Strona1Click(TObject *Sender)
{
        //Form2->Visible=true;
        Form2->ShowModal();
}
//---------------------------------------------------------------------------
void __fastcall TForm1::Autor1Click(TObject *Sender)
{
        //ShellExecute(NULL,"open","http://miroslawzelent.pl",NULL,NULL,SW_SHOWNORMAL);       
}
//---------------------------------------------------------------------------

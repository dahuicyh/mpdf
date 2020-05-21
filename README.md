mPDF is a PHP class which generates PDF files from UTF-8 encoded HTML. It is based on [FPDF](http://www.fpdf.org/)

$mPdf = new mPDF('UTF-8', 'A4', 14, '', 10, 10, 15, 1);
$mPdf->SetDisplayMode('real');
$mPdf->autoScriptToLang = true;
$mPdf->autoLangToFont = true;
$mPdf->WriteHTML($html);
if ($logo) {
	$mPdf->Image($logo, 130, 135, 41, 27);
}
if ($name) {
	$mPdf->Image($name, 63, 138, 20, 8);
}
if (!$pdfName) {
	$pdfName = self::AGREEMENT_PATH . rand(1, 1000000) . '.pdf';
}
$mPdf->Output($pdfName);

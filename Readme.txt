
    @csrf
    
    Upload



Route::post('image-upload', 'ImageUploadController@imageUploadPost');


public function imageUploadPost()
{
    request()->validate([
        'image' => 'required|image|mimes:jpeg,png,jpg,gif,svg|max:2048',
    ]);

    $imageName = time().'.'.request()->image->getClientOriginalExtension();
    request()->image->move(public_path('images'), $imageName);
}





<section class="section about">
	<div class="container">
		<div class="row align-items-center">
			<div class="col-lg-4 col-sm-6">
				<div class="about-img">
					<img src="images/about/im-1.jpg" alt="" class="img-fluid">
					<img src="images/about/im-2.jpg" alt="" class="img-fluid mt-4">
				</div>
			</div>
			<div class="col-lg-4 col-sm-6">
				<div class="about-img mt-4 mt-lg-0">
					<img src="images/about/im-3.jpg" alt="" class="img-fluid">
				</div>
			</div>
			<div class="col-lg-4">
				<div class="about-content pl-4 mt-4 mt-lg-0">
					<h2 class="title-color">Saúde <br>E Cuidados Pessoais</h2>
					<p class="mt-4 mb-5">Nos dedicamos à fornecer o melhor serviço e cuidados médico para sí e sua família.</p>

					<a href="service.html" class="btn btn-main-2 btn-round-full btn-icon">Serviços<i class="icofont-simple-right ml-3"></i></a>
				</div>
			</div>
		</div>
	</div>
</section>
## Calculate aspect ratio for form submission
```
    $(document).on('beforeSubmit', '#form--identity', function(e) {
        let form = this;

        e.preventDefault();

        let fileInput = $(this).find("input[type=file]")[0],
            file = fileInput.files && fileInput.files[0];
        
        if (file) {
            var img = new Image();

            img.src = window.URL.createObjectURL( file );

            img.onload = function() {
                var width = img.naturalWidth.toFixed(2),
                    height = img.naturalHeight.toFixed(2);

                window.URL.revokeObjectURL( img.src );
                
                console.log(width, height);
                let magic_number = 1.78;
                let aspect_ratio = (height / width).toFixed(2);
                console.log(aspect_ratio);

                if (aspect_ratio == magic_number) {
                    return true;
                } else {
                    alert("Image is not 9:16 (Portrait) aspect ratio");
                    return false;
                }
            }
            return false;
        } else {
            return false;
        }
    });
  ```

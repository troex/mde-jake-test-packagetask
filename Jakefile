desc('testz')
task('testbuild', function(){
    console.log('start test build');
    var t = new jake.PackageTask('elfinder', 'buildtest', function(){
        var files = ['Changelog'];
        this.packageFiles.include(files);
        this.needTarGz = true;
        console.log('finish');
    });
});

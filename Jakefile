var version = 'test';
var fs = require('fs');

desc('prepare')
task('prepare', function(){
    console.log('preparing');
    var t = new jake.PackageTask('elfinder', version, function(){
        var files = ['Changelog'];
        this.packageFiles.include(files);
        this.needTarGz = true;
        console.log('prepare finish');
    });
});

desc('release')
task('release', ['prepare', 'package'], function(){
    console.log('go');
});

desc('version');
task('version', function(){
    jake.exec(['git describe --always > .version'], function(){
        version = fs.readFileSync('.version').toString().replace(/\n$/, '');
        fs.unlinkSync('.version');
        jake.Task['release'].invoke();
    });
});

# Build a HTML version of the manpages

class ManEntry
    attr :title, :section, :subsection
    
    def initialize title, section, subsection
        @title = title
        @section = section
        @subsection = subsection
    end
    
    def ManEntry.from_pathname pathname
        basename = File.basename pathname.chomp
    
        if basename =~ /(.+)\.(\d)([^.]*)(?:\.gz)?/
            return ManEntry.new $1, $2, $3
        else
            return nil
        end
    end
    
    def == other
        other.title == @title and other.section == @section and other.subsection == @subsection
    end
    
    def to_s
        "#{@title}(#{section}#{subsection})"
    end
end

build_dir = "./build"
man_location = "/usr/share/man/man2/*"

task :man do
    FileList.new(man_location).each do |pathname|
        entry = ManEntry.from_pathname pathname
        
        if not entry.nil?
            # Skip the subsections for now, too long to build
            if entry.subsection.length == 0
                man_dir = File.join build_dir, "man#{entry.section}"
                man_name = "#{entry.title}.#{entry.section}#{entry.subsection}.html"
                man_path = File.join(man_dir, man_name)
                
                if not Dir.exists? man_dir
                    mkdir_p man_dir
                end
                
                $stderr.puts entry
                system "./webmanner --style '/man-style.css' #{entry.section}#{entry.subsection} #{entry.title} > #{man_path}"
            end
        end
    end
end
